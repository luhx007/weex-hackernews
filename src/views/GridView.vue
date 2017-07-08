<template>
  <div>
    <app-header></app-header>
    <div class="grid-container">
      <div v-for="(v, i) in list" v-bind:key="i" class="row">
        <div v-for="(text, k) in v" v-bind:key="k" class="item" @click="showText(text)">
          <div>
            <text>{{text}}</text>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.grid-container {
  height: 90%;
  overflow: auto;
}
.item {
  flex: 1;
  justify-content: center;
  align-items: center;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin: 5px;
}

.row {
  flex-direction: row;
  height: 280px;
}
</style>
<script>
import AppHeader from '../components/app-header.vue'
export default {
  components: { AppHeader },
  data: function () {
    return {
      list: [
        ['A', 'B'],
        ['C', 'D'],
        ['E', 'F'],
        ['G', 'H'],
        ['I', 'j']
      ]
    }
  },
  methods: {
    showText(text) {
      console.log('You clicked ' + text)
    }
  }
}
</script>