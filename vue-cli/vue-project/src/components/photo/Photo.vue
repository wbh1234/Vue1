<template>
    <div class="photo">
        <common-header title="photo" bgColor="orange" nav="<"></common-header>
        <ul class="photo-list">
            <li v-for = "(obj, index) in photoData" :key="index">
                <router-link :to="`/photo_detail/ ${index}`">
                    <img :src="obj.src" alt="">
                </router-link>
                
            </li>
        </ul>
        <common-footer bgColor="orange"></common-footer>
    </div>
</template>
<script>
    import CommonHeader from "../common/CommonHeader"
    import CommonFooter from "../common/CommonFooter"
    // import {mapState,mapAction} from 'vuex';
    import Axios from 'axios'
    export default {
        data(){
            return {
                photoData:[]
            }
        },
        mounted(){
            Axios.get('/static/photo-data.json')
            .then(res=>{
                this.photoData =res.data.photoData;
                // this.changeData(res.data.photoData);
            });
        },
        // computed:{
        //     ...map(['photoData'])
        // },
        // methods:{
        //     ...mapActions(['changeData'])
        // },
        components:{
            CommonHeader,
            CommonFooter
        }
    }
</script>
<style>
    .photo-list{
        margin-top: 1rem;
        margin-bottom: 1rem;
        overflow: hidden;
    }
    .photo-list li{
        width: 50%;
        float: left;
    }


</style>