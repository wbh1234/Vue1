<template>
    <div class="book">
        <common-header title="book" bgColor="rgb(121, 85, 72)" nav="<"></common-header>
        <swipe class="my-swipe">
            <swipe-item class="slide1"></swipe-item>
            <swipe-item class="slide2"></swipe-item>
            <swipe-item class="slide3"></swipe-item>
        </swipe>
        <common-footer bgColor="rgb(121, 85, 72)"></common-footer>
    </div>
</template>
<script>
    import CommonHeader from "../common/CommonHeader"
    import CommonFooter from "../common/CommonFooter"
    import {Swipe,SwipeItem} from 'vue-swipe'
    export default {
        components:{
            CommonHeader,
            CommonFooter,
            Swipe,
            SwipeItem
        }
    }
</script>
<style>
    @import "../../assets/css/vue-swipe.css";
    .my-swipe{
        height: 200px;
        /* color: #fff; */
        font-size: 30px;
        text-align: center;
        margin-top: 1rem;
    }
    .slide1{
        /* background: url('https://img3.doubanio.com/lpic/s6989253.jpg'); */
        background-color: blue;
        color: #fff;
    }
    .slide2 {
        /* background: url('https://img3.doubanio.com/lpic/s24468373.jpg'); */
        background-color:pink;
        color: #fff;
    }
    .slide3 {
        /* background:  url('https://img3.doubanio.com/lpic/s27102925.jpg'); */
        background:red;
        color: #fff;
    }


</style>