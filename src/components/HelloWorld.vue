<template>
  <div class="hello">
    <button @click="go(1)">go page1</button>
    <button @click="go(2)">go page2</button>
    <button @click="go(3)">go page3</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    go(value) {
      if(value==2) {
        this.$router.push({
          path:"/page2",
          query: {
            name: "page2name"
          }
        })
      }else if(value==1){
        this.$router.push({
          name:"page1",
          params: {
            name: "page1name"
          }
        })
      }else if(value == 3) {
        this.$router.push({
          path: `/page3/${value}`,
        })
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
