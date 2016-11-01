<template lang="html">
  <div class="app">
    <div class="app__left">

      <h1 class="app__left-title">Build Your Monster</h1>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/body-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/mouth-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>

      <div class="img-switcher">
        <button class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img src="/monsters/eyes-1.png" alt="part.title"/>
        </div>
        <button class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>

    </div>
    <div class="app__right">
      <div class="main">
        <div class="monster">
          <img class="monster-img monster-body" src="/monsters/body-1.png" alt="" />
          <img class="monster-img monster-mouth" src="/monsters/mouth-1.png" alt="" />
          <img class="monster-img monster-eyes" src="/monsters/eyes-1.png" alt="" />
        </div>
      </div>
        <div class="monster__results">
          <div class="monster monster__bottom">
            <img class="monster-img monster-body bottom__body" src="/monsters/body-1.png" alt="" />
            <img class="monster-img monster-mouth bottom__mouth" src="/monsters/mouth-1.png" alt="" />
            <img class="monster-img monster-eyes bottom__eyes" src="/monsters/eyes-1.png" alt="" />
          </div>
          <div class="monster monster__bottom">
            <img class="monster-img monster-body bottom__body" src="/monsters/body-1.png" alt="" />
            <img class="monster-img monster-mouth bottom__mouth" src="/monsters/mouth-1.png" alt="" />
            <img class="monster-img monster-eyes bottom__eyes" src="/monsters/eyes-1.png" alt="" />
          </div>
          <div class="monster monster__bottom">
            <img class="monster-img monster-body bottom__body" src="/monsters/body-1.png" alt="" />
            <img class="monster-img monster-mouth bottom__mouth" src="/monsters/mouth-1.png" alt="" />
            <img class="monster-img monster-eyes bottom__eyes" src="/monsters/eyes-1.png" alt="" />
          </div>
        </div>
    </div>
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
