<template>
  <div class="tags-form">
    <div class="form">
      <input-style-1
        :placeholder="'Enter your Youtube video title to generate tags'"
        :autofocus="true"
        v-on:emit-value="setSearchTerm"
				v-on:emit-enter="fetchTags"
      />
    </div>
    <div class="tags-result" v-if="showTagsResults">
      <tag v-for="(tag, index) in tags" :key="index">
        {{ tag }}
      </tag>
    </div>
    <button class="btn-style-1" style="margin:15px 0px;" v-if="showTagsResults">
      Copy to Clipboard
    </button>
  </div>
</template>

<script>
import axios from 'axios';
import InputStyle1 from "./InputStyle1.vue";
import Tag from "./Tag.vue";


export default {
  name: "TagsForm",
  components: { InputStyle1, Tag },
  data() {
    return {
      tags: [],
      searchTerm: "",
    };
  },
  computed: {
    showTagsResults: function() {
      return this.tags.length > 0;
    },
  },
  methods: {
    setSearchTerm(val) {
      this.searchTerm = val;
    },
    fetchTags(){
      if (this.searchTerm == "") {
        alert("Please enter the name of video");
				return;
      }

			var dataObj = this;
			// Fetch Data using API
			let apiEndPoint = `https://random-word-api.herokuapp.com/word?number=10`;
			axios.get(apiEndPoint)
				.then(function (response) {
					dataObj.tags = response.data;
				})
				.catch(function (error) {
					// handle error
					console.log(error);
				})
				.then(function () {
					// always executed
				});
      console.log("fetch records");
    },
  },
};
</script>
