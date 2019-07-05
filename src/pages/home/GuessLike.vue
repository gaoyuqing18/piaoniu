<template>
    <div>
         <div class="guess-like" style="">
            <div class="guess-like__title">猜你喜欢</div>

            <div class="guess-like__wrap">  
                <guess-like-item v-for="item in gusslist" :key="item.id" :movie="item">

                </guess-like-item>
            </div>
         </div>
    </div>
</template>

<script>
import http from '@/utils/http.js'
import guessLikeItem from '@/components/GuessLikeItem'
export default {

    data() {
        return {
        gusslist: {}  //定义一个list接收请求的数据
        }
    },
    components:{
        guessLikeItem
    },
   async mounted() {
      let result =await http.get({
          url: '/api/v2/home/recommends',
          params: {
              pageIndex :1,
              pageSize :10,
          }
      }) 
      this.gusslist = result.data ,
       console.log(result)
    },
// created() {
//     this.pageIndex = 1
//     this.pagesize = 10
//     //this.isFinished = true // 是否可以加载下一页（true：可以加载）
//   },
//    methods: {
//     async loadData(pageIndex, pagesize) {
//       return await http.get({
//         url: '/api/v1/activities/hot?pageIndex=1&pageSize=10',
//         // params: {
//         //   pageIndex=1,
//         //   pageSize=10
//         // }
//       })
//     },
  
// },
//    async mounted() {
//     let result = await this.loadData(this.pageIndex, this.pagesize)
//     console.log(result)
//     this.list = result
//     //this.page++

//   },

}
</script>

<style lang="stylus">
.guess-like {
    margin-top: 38px;
}
.guess-like__title {
    font-size: 18px;
    color: #565656;
    padding: 0 14px;
}

</style>
