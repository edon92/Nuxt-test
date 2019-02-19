<template>
  <div class="search">
    <ul v-show="list">
      <li v-for="(item, index) in list" :key="index">{{item}}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      list: []
    }
  },
  // async created() {
  //   let {status, data: {list}} = await axios.get('http://localhost:3000/city/list')
  //   if (status === 200) {
  //     this.list = list
  //   }
  // }
  async asyncData() {
    let {status, data: {list}} = await axios.get('http://localhost:3000/city/list')
    if (status === 200) {
      return {
        list
      }
    }
  }
}
</script>

<style scoped>
</style>
