<template>
    <div v-if="notifications.length==0">
        <app-empty-notify></app-empty-notify>
    </div>
    <div v-else>
        <ul class="list-group list-group-flush">
            <small>
                <li class="list-group-item" :key="index" v-for="(notify,index) in notifications">{{notify}}</li>
            </small>
        </ul>
    </div>
</template>

<script>

import Emptynotify from './EmptyNotify.vue'

export default {
    name : 'CategoryNotification',
    props : {
        type : String,
        notifications : Array
    },
    components:{
        appEmptyNotify : Emptynotify
    }
}
</script>

<style scoped>

small{
    max-height: 50vh;
    overflow-y:auto;
    -webkit-overflow-scrolling: touch;
}

</style>