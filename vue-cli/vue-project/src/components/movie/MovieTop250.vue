<template>
     <div class='list'>
        <movie-list v-for="(obj,index) in movieList" :key="index" :title="obj.nm"
         :year="obj.snum" :img = "obj.img" :avg="obj.sc" :desc="obj.cat">
        </movie-list>
      </div>

</template>
<script>
    import MovieList from './MovieList'
    import Axios from 'axios'
    export default{
        data (){
            return {
                movieList: [],
            }
        },
        mounted(){
            let _this =this;
            window.onscroll = function(){
                let  scrollTop =document.documentElement.scrollTop;
                let clientHeight = document.documentElement.clientHeight;
                let htmlHeight = document.documentElement.scrollHeight;
                if(scrollTop + clientHeight >= htmlHeight){
                    _this.isShow = true;
                    _this.loadData();
                }
            }
            this.loadData();
        },
        methods:{
            loadData(){
                Axios.get(API_PROXY + "http://m.maoyan.com/movie/list.json?type=hot&offset="+this.movieList.length+"&limit=10")
                    .then((res)=>{
                    this.movieList = this.movieList.concat(res.data.data.movies);
                    this.isShow    = false;
                 });
            }
        },
       components:{
           MovieList
       } 
    }
</script>
<style>
    .list{
        margin: 2rem 0 1.6rem;
    }
    .loading{
        margin-bottom:  1rem;
        text-align: center;
    }
</style>