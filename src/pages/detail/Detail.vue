<template>
  <div>
    <detail-banner
      :signName="signName"
      :bannerImg = "bannerImg"
      :bannerImgs = "gallaryImgs"
    ></detail-banner>
    <detail-header></detail-header>
    <detail-list
      :list="list"
      :len="len"
    ></detail-list>
  </div>
</template>

<script>
  import DetailHeader from './components/Header'
  import DetailBanner from './components/Banner'
  import DetailList from './components/List'
  import axios from 'axios'
  export default {
    name: "Detail",
    components: {
      DetailHeader,
      DetailBanner,
      DetailList
    },
    data () {
      return {
        signName: '',
        bannerImg: '',
        gallaryImgs: [],
        list: [],
        len: []
      }
    },
    methods: {
      handleGetDetail () {
        axios.get('/api/detail.json',{
          params: {
            id: this.$route.params.id
          }
        })
          .then(this.handleGetDetailSucc)
      },
      handleGetDetailSucc (res) {
        res = res.data
        if (res.ret && res.data){
          const data = res.data
          this.signName = data.signName
          this.bannerImg = data.bannerImg
          this.gallaryImgs = data.gallaryImgs
          this.list = data.categoryList
          this.len = new Array(this.list.length).fill(false)
        }
      },
      handleChange(index){
        this.len[index] = !this.len[index]
      }
    },
    mounted (){
      console.log(this.$route)
      this.handleGetDetail()
    }
  }
</script>

<style lang="stylus" scoped>

</style>

