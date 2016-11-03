<template lang="html">
  <div class="app">
    <div class="app__left">

      <h1 class="app__left-title">Build Your Monster</h1>

      <div class="img-switcher">
        <button @click="updatePart('body', - 1)" class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img :src="'/monsters/' + monsterParts.body[selected.body] + '.png'" alt="part.title"/>
        </div>
        <button @click="updatePart('body', + 1)" class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>

      <div class="img-switcher">
        <button @click="updatePart('mouth', - 1)" class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img :src="'/monsters/' + monsterParts.mouth[selected.mouth] + '.png'" alt="part.title"/>
        </div>
        <button @click="updatePart('mouth', + 1)" class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>

      <div class="img-switcher">
        <button @click="updatePart('eyes', - 1)" class="btn"><i class="fa fa-caret-left fa-2x" aria-hidden="true"></i></button>
        <div class="frame">
          <img :src="'/monsters/' + monsterParts.eyes[selected.eyes] + '.png'" alt="part.title"/>
        </div>
        <button @click="updatePart('eyes', + 1)" class="btn"><i class="fa fa-caret-right fa-2x" aria-hidden="true"></i></button>
      </div>
      <form class="left-text" @submit.prevent="saveMonster">
        <input type="text" class="left-text__input" placeholder="Name Your Creation" v-model="selected.name">
        <button class="left-text__btn">SAVE FAVORITE</button>
      </form>
    </div>
    <div class="app__right">
      <div class="main">
        <div class="monster">
          <img class="monster-img" :src="'/monsters/' + monsterParts.body[selected.body] + '.full.png'" alt="" />
          <img class="monster-img" :src="'/monsters/' + monsterParts.mouth[selected.mouth] + '.full.png'" alt="" />
          <img class="monster-img" :src="'/monsters/' + monsterParts.eyes[selected.eyes] + '.full.png'" alt="" />
        </div>
      </div>
        <div class="monster-results">
          <div class="monster-results__item" v-for="favorite in favorites">
            <div class="monster">
              <img class="monster-img" :src="'/monster' + monsterParts.body[favorite.body] + '.full.png'" alt="" />
              <img class="monster-img" :src="'/monster' + monsterParts.mouth[favorite.mouth] + '.full.png'" alt="" />
              <img class="monster-img" :src="'/monster' + monsterParts.eyes[favorite.eyes] + '.full.png'" alt="" />
            </div>

            <h2>{{ favorite.name }}</h2>
          </div>
          <div class="monster-results__item">
            <div class="monster">
              <img class="monster-img" src="/monsters/body-1.full.png" alt="" />
              <img class="monster-img" src="/monsters/mouth-1.full.png" alt="" />
              <img class="monster-img" src="/monsters/eyes-1.full.png" alt="" />
            </div>

            <h2>Hello Dennis</h2>
          </div>
          <div class="monster-results__item">
            <div class="monster">
              <img class="monster-img" src="/monsters/body-1.full.png" alt="" />
              <img class="monster-img" src="/monsters/mouth-1.full.png" alt="" />
              <img class="monster-img" src="/monsters/eyes-1.full.png" alt="" />
            </div>

            <h2>Hello Dennis</h2>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue';
import monsterParts from './monster-parts';

export default Vue.extend({
  data() {
    return {
      selected: {
        body: 0,
        mouth: 0,
        eyes: 0,
        names: '',
      },
      monsterParts,
      favorites: [],
    };
  },

  mounted() {
    this.getFavorites();
  },


  methods: {

    getFavorites() {
      fetch('http:tiny-tn.herokuapp.com/collections/db-monsters')
        .then((r) => r.json())
        .then((favorites) => {
          this.favorites = favorites;
        });
    },

    updatePart(partName, difference = 1) {
      this.selected[partName] = (this.selected[partName] + difference) % this.monsterParts[partName].length;
    },

    saveMonster() {
      fetch(`http:tiny-tn.herokuapp.com/collections/db-monsters`, {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify(this.selected)
        })
        .then((r) => r.json())
        .then((favorites) => {
          this.favorites = [favorite, ...this.favorites];
          this.selected = {
            name: '',
            body: 0,
            eyes: 0,
            mouth: 0,
          };
        });
    },


  },
});
</script>
