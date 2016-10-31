<template lang="html">
  <div class="app">
    <div class="app__left">

      <h1>Build Your Monster</h1>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/body-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></button>
      </div>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/mouth-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></button>
      </div>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/eyes-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></button>
      </div>

    </div>
    <div class="app__right"></div>
  </div>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  data() {
    return {
      getParts: '',
    }
  },

  mounted: {},


  methods: {

  }
});
</script>
