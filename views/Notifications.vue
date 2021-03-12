<template>
    <div class="container-fluid">
        <div class="row ads mb-2">
            <div class="col card-deck">
                <div class="card indiBorder text-left">
                    <div class="card-body">
                        <h5 class="card-title">Your ad goes here</h5>
                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                        <a href="#" class="card-link">Ad link</a>
                    </div>
                </div>
                <div class="card indiBorder text-left">
                    <div class="card-body">
                        <h5 class="card-title">Your ad goes here</h5>
                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                        <a href="#" class="card-link">Ad link</a>
                    </div>
                </div> 
                <div class="card indiBorder text-left">
                    <div class="card-body">
                        <h5 class="card-title">Your ad goes here</h5>
                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                        <a href="#" class="card-link">Ad link</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="row notify">
            <div class="col card-deck">
                <div class="card indiBorder">
                    <div class="card-header">
                        Netwrok Notifications
                    </div>
                    <app-category-notification :notifications="miscNotify"></app-category-notification>
                </div>
                <div class="card indiBorder">
                    <div class="card-header">
                        Younnection Notifications
                    </div>
                    <app-category-notification :notifications="conNotify"></app-category-notification>
                </div>
                <div class="card indiBorder">
                    <div class="card-header">
                        Message Notifications
                    </div>
                    <app-category-notification :notifications="msgNotify"></app-category-notification>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import CategoryNotification from  '../components/CategoryNotification.vue'

export default {
    name:'Notifications',
    components : {
        'appCategoryNotification' : CategoryNotification
    },
    data(){
        return{
            miscNotify : [],
            conNotify : ['Yonnection request from Chin Ya Russell','Chin Ya Russell accepted your younnection'
            ,'Yonnection request from Shivaleela Hubli','Shivaleela Hubli accepted your younnection'],
            msgNotify : ['Message from Chin Ya Russell'],

        }
    }
}
</script>

<style scoped>


</style>