<template>
    <div class="bg-white indiBorder">
        <h6>{{company}}</h6>
        <p>Title : {{title}}</p>
                <p>Type : {{employment}}</p>
                <p>Location : {{location}}</p>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="Current job" id="" :checked="isCurrent"> Current job
                </div>
                <div class="form-group">
                    <p>Start date: {{startDate}}</p>
                </div> 
                <div class="form-group">
                    <p>End date: {{endDate}}</p>
                </div> 
                <div class="form-group">
                    <p class="text-justify">Description: {{description}}</p>
                </div>
    </div>
</template>

<script>
export default {
    name:'Work',
    props: {
        title : String,
        employment : String,
        company : String,
        location : String,
        isCurrent : Boolean,
        startDate : Date,
        endDate : Date,
        description : String
    }
}
</script>

<style scoped>

hr.diff{
    border: 1px solid yellowgreen;
}
</style>