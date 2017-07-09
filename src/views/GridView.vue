<template>
  <div class="grid-view" append="tree">
    <app-header></app-header>
    <list>
      <cell v-for="(v, i) in list" :key="i" class="row">
        <div v-for="(text, k) in v" :key="k" class="item" @click="showText(text)">
          <text>{{text}}</text>
        </div>
      </cell>
    </list>
  </div>
</template>
<style scoped>
.grid-view {
  height: 100%
}
.item {
  flex: 1;
  justify-content: center;
  align-items: center;
  border-top-width: 1px;
  border-top-style: solid;
  border-top-color: #ccc;
  border-right-width: 1px;
  border-right-style: solid;
  border-right-color: #ccc;
  border-bottom-width: 1px;
  border-bottom-style: solid;
  border-bottom-color: #ccc;
  border-left-width: 1px;
  border-left-style: solid;
  border-left-color: #ccc;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
  margin-top: 5px;
  margin-right: 5px;
  margin-bottom: 5px;
  margin-left: 5px;
}
.row {
  flex-direction: row;
  height: 280px;
}
</style>
<script>
import AppHeader from '../components/app-header.vue'

var modal = weex.requireModule('modal')

export default {
  components: { AppHeader },
  data: function () {
    return {
      list: [
        ['NEWS', 'QUERY'],
        ['FAQ', 'PRODUCTS'],
        ['JOBS', 'QUIZ'],
        ['G', 'H'],
        ['I', 'j'],
        ['J', 'K'],
        ['L', 'M']
      ]
    }
  },
  methods: { 
    showText(text) {
      modal.toast({
        message: 'You clicked ' + text,
        duration: 0.5
      })
      console.log('You clicked ' + text)
    }
  }
}
</script>