<template>
  <div id="app">
    <nav id="navbar">
      <div class="container">
        <div class="navbar-content">
          <div class="logo-wrapper">
            <img src="@/assets/images/logo.png" alt="taggz logo" class="logo">
          </div>
          <div class="links-wrapper">
            <a href="" class="navbar-link youtube">
              <img src="@/assets/images/youtube-32.png" alt="youtube">
              Youtube
            </a>
            <a href="" class="navbar-link twitter">
              <img src="@/assets/images/twitter-32.png" alt="youtube">
              Twitter
            </a>
            <a href="" class="navbar-link tiktok">
              <img src="@/assets/images/tiktok-32.png" alt="youtube">
              Tiktok
            </a>
          </div>
        </div>
      </div>
    </nav>

    <div id="main">
      <div class="container">
        <!-- Tags Form -->
        <div class="tags-form">
          <div class="form">
            <div class="input-style-1">
              <img src="@/assets/images/logo-mini.png" alt="Taggz Logo" class="icon">
              <input type="text" placeholder="Enter your Youtube video title to generate tags">
              <button>
                <img src="@/assets/images/magnifier.png" alt="Search Button">
              </button>
            </div>
          </div>
          <div class="tags-result">
            <div class="tag-style-1" v-for="i in 50" :key="i">
              <div class="tag-title">HTML Course</div>
              <a href="javascript:void(0)" class="times">X</a>
            </div>
          </div>
          <button class="btn-style-1" style="margin:15px 0px;">Copy to Clipboard</button>
        </div>
        <!-- End Tags Form -->
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
}
</script>
