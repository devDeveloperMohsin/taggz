<template>
  <div class="input-style-1">
    <img src="@/assets/images/logo-mini.png" alt="Taggz Logo" class="icon" />
    <input
      type="text"
      :placeholder="placeholder"
			:autofocus="autofocus"
			v-model="inputVal"
			@change="emitInputVal"
			@keyup.enter="$emit('emit-enter')"
    />
    <button @click="$emit('emit-enter')">
      <img src="@/assets/images/magnifier.png" alt="Search Button" />
    </button>
  </div>
</template>

<script>
export default {
  name: "InputStyle1",
	props: ['placeholder', 'autofocus'],
	data(){
		return {
			inputVal: '',
		}
	},
	methods: {
		emitInputVal: function(){
			this.$emit('emit-value', this.inputVal);
		}
	}
};
</script>
