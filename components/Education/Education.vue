<template>
    <div class="bg-white indiBorder">
        <h6>{{school}}</h6>
                <p>Degree : {{degree}}</p>
                <p>Major : {{major}}</p>
                <div class="form-group">
                    <p>Start date: {{eduStart}}</p>
                </div> 
                <div class="form-group">
                    <p>End date: {{eduEnd}}</p>
                </div> 
                <div class="form-group">
                    <p class="text-justify">Activities and Societies: {{activitiesSocieties}}</p>
                </div>
    </div>
</template>

<script>
export default {
    name : 'Education',
    props:{
        school: String,
        degree : String,
        major: String,
        eduStart : Date,
        eduEnd : Date,
        activitiesSocieties : String
    }
}
</script>

<style>
hr.diff{
    border: 1px solid yellowgreen;
}
</style>