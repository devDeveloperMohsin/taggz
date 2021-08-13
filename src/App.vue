<template>
  <div id="app">
    <navbar />    

    <div id="main">
      <div class="container">
        <!-- Tags Form -->
        <tags-form />
        <!-- End Tags Form -->
      </div>
    </div>
  </div>
</template>

<script>

import Navbar from './components/Navbar.vue';
import TagsForm from './components/TagsForm.vue';
export default {
  name: 'App',
  components: {Navbar, TagsForm}
}
</script>
