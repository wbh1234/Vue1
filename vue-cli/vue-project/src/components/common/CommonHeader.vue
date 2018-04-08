<template>
  <div class="header" :style="{background:bgColor}">
      <slot>
          
      </slot>
    <button :style="{background:bgColor}" @click='back'>{{nav}}</button>
    <h2>{{title}}</h2>


  </div>
  
</template>

<script>
export default {
  props:['title','bgColor','nav'],
  methods:{
      back(){
          history.go(-1);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .header{
        height: 1rem;
        display: flex;
        color: white;
        position: fixed;
        top: 0;
         width: 100%;
    }
    .header button{
        width: 1rem;
        height: 1rem;
        /* background: rgb(33,150,243); */
        color: white;
        float: left;
        border: none;
        outline: none;
    }
    .header h2{
        float: left;
        flex: 1;
        color: white;
        text-align:center;
        text-indent: -1rem;
    }
</style>
