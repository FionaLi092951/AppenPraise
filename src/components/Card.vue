<template>
  <div class="card-wrapper">
    <!-- {{imageType}} -->
    <div class="header">
      <img :src="'../../static/'+index+'.jpg'">
      <h1 class="title">{{name}}</h1>
    </div>
    <p class="desc">{{description}}</p>
  </div>
</template>

<script>
export default {
  props: {
    index: {
      type: Number,
      default: 0,
    },
    praise: {
      type: String,
      default: '/appenpraise @(John) did something great! Congratulations to him!'
    }
  },
  data () {
    return {
      imageType: 0,
      name: '',
      description: ''
    }
  },
  created () {
    this.initializeData()
  },
  watch: {
    praise () {
      this.initializeData()
    }
  },
  methods: {
    initializeData () {
      this.imageType = Math.floor(Math.random() * 2)
      this.name = ''
      this.description = ''
      if (this.praise.indexOf('/appenpraise') === -1) {
        return
      }
      const charAt = this.praise.indexOf('@')
      const charParenthis = this.praise.indexOf(')')
      this.name = `@${this.praise.substring(charAt + 2, charParenthis)}`
      this.description = this.praise.substring(charParenthis + 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.card-wrapper{
  width: 300px;
  height: 400px;
  margin: 0px 10px 10px 0px;
  background-color:#FFFFFF;
  border: 1px solid #E9E9E9;
  border-radius: 5px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  &:hover{
    box-shadow: 0px 5px 10px 0px rgba(0,0,0,0.15);
  }
  .header{
    display: flex;
    align-items: center;
    padding: 0px 20px;
    img{
      width: 70px;
      border-radius: 100px;
      // height: 50px;
    }
    .title{
      margin-left: 20px;
      display: inline-block;
      color: #333333;
      font-size: 16px;
    }
  }
  .desc{
    flex: 1;
    // height: calc(100% - 64px);
    overflow-y: auto;
    color: #666666;
    font-size: 20px;
    line-height: 30px;
  }
}
</style>
