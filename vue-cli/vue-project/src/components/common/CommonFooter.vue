<template>
  <div class="footer" :style="{background:bgColor}">
    <ul>
      <li><router-link to='/Movie'>电影</router-link></li>
      <li><router-link to='/Music'> 音乐</router-link></li>
      <li><router-link to='/Book'>书籍</router-link></li>
      <li><router-link to='/Photo'>图片</router-link></li>
    </ul>

  </div>
  
</template>

<script>
export default {
  props:['bgColor'],
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .footer{
        height: 1rem;
        /* background: rgb(33,150,243); */
        color: white;
        position: fixed;
        bottom: 0;
        width: 100%;
    }
    .footer ul{
      display: flex;
    }
    .footer li{
      flex:1;
      color: white;
      line-height:1rem;
      text-align:center;
      
    }
    .footer li a{
      color:gray;
    }
    .footer li a.router-link-active{
      color:white;
    }
</style>
