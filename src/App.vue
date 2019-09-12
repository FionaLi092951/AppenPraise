<template>
  <div id="app">
    <div class="card-list">
      <Card v-for="(item, index) in praiseList"
      :praise="item" :index="index" :key="index"/>
    </div>
  </div>
</template>

<script>
import Card from './components/Card'

export default {
  name: 'App',
  data () {
    return {
      praiseList: [
        '/appenpraise @(John) did something great! Congratulations to him! did something great! Congratulations to him!did something great! Congratulations to him!did something great! Congratulations to him!did something great! Congratulations to him! did something great! Congratulations to him!did something great! Congratulations to him!did something great! Congratulations to him!did something great! Congratulations to him!',
        '/appenpraise @(John) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!',
        '/appenpraise @(Fangfang Li) did something great! Congratulations to him!'
      ]
    }
  },
  components: {
    Card
  }
}
</script>

<style lang="scss" scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding-top: 20px;
  .card-list{
    padding-left: 10px;
    display: flex;
    flex-wrap: wrap;
    // background-color: yellow;
  }
}
</style>
