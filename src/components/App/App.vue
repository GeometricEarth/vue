<template>
  <div class="app">
  <!-- <div id="app">
    <img src="../../assets/logo.png">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul> -->
  
  
  <list></list>
  <field v-on:newQuestion='add'></field>
  </div>
</template>

<script>
import Field from '../Field/Field.vue';
import List from '../List/QuestionList.vue';

// this.$on('newQuestion', add);

export default {
  name: 'app',
  components: {
    'field': Field,
    'list' : List,
  },
  data () {
    return {

    }
  },
  methods: {
    add(evt) {
        // List.add(evt);
        console.log('bb');
      
    }
  },
}
</script>

<style>
.app{
    margin: 0 auto;
    padding-top: 48px;
    width: 800px;
    /* display: flex; */
    /* flex-direction: row; */
}
</style>
