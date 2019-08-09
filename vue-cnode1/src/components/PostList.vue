<template>
    <div>
       <div class="loading" v-if="isLoading">
           <img src="../assets/loading.gif" alt="">
       </div>
       <div class="listStyle">
           <ul>
               <li>xxx</li>
           </ul>
       </div>
    </div>
</template>

<script>
export default {
  name: 'PostList',
  data () {
    return {
      isLoading: false
    }
  },
  methods: {
    getData () {
      this.$axios.get('https://cnodejs.org/api/v1/topics', {
        page: 1,
        limit: 20
      }).then((response) => {
        this.isLoading = false // 加载成功后去除动画
        console.log(response)
      })
        .catch((err) => {
          console.log(err)
        })
    }
  },
  // 在 Vue 实例挂载到 DOM 之前获取数据
  beforeMount () {
    this.isLoading = true
    this.getData()
  },
  components: {
  }
}
</script>

<style scoped>

</style>
