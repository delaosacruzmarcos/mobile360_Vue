<template>
    <div class="row d-flex flex-column justify-content-start">
        <h5 class="text-left">Education
            <i class="fas fa-plus-circle" data-toggle="modal" data-target="#eduModal"></i>
        </h5>
            <div class="modal fade" id="eduModal" tabindex="-1" role="dialog"               aria-labelledby="exampleModalLabel" aria-hidden="true">
                <div class="modal-dialog" role="document">
                    <div class="modal-content">
                        <div class="modal-header">
                            <h5 class="modal-title" id="exampleModalLabel">Education</h5>
                            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                            </button>
                        </div>
                    <div class="modal-body text-left">
                        <form>
                            <div class="form-group">
                                <label for="university">University</label>
                                <input type="text" class="form-control" id="university" placeholder="University">
                            </div>
                            <div class="row">
                                <div class="col form-group">
                                    <label for="degree">Degree</label>
                                    <input type="text" class="form-control" id="degree" placeholder="Degree">
                                </div>
                                <div class="col form-group">
                                    <label for="major">Major</label>
                                    <input type="text" class="form-control" id="major" placeholder="Major">
                                </div>
                            </div>
                            <div class="form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                                <label class="form-check-label" for="exampleCheck1">Current Education?</label>
                            </div>
                            <div class="row">
                                <div class="col form-group">
                                    <label for="eduStart">Start Date</label>
                                    <input type="date" class="form-control" id="eduStart">
                                </div>
                                <div class="col form-group">
                                    <label for="eduEnd">End Date</label>
                                    <input type="date" class="form-control" id="eduEnd">
                                </div>
                            </div>
                            <div class="form-group">
                                <label for="summary">Actvities and Societies</label>
                                <textarea class="form-control" id="summary"></textarea>
                            </div>
                            <button data-dismiss="modal" type="submit" @click.prevent="addEducation()" class="btn btn-primary">Add Education</button>
                        </form>
                    </div>
                    </div>
                </div>
            </div>
        <div class="text-left" :key=index v-for="(qualification,index) in educations">
            <education class="m-1 p-2 rounded" :school="qualification.school"
            :degree="qualification.degree" :major="qualification.field" 
            :eduStart="qualification.startYear"
            :eduEnd="qualification.endYear" :cgpa="qualification.cgpa" 
            :activitiesSocieties="qualification.activitiesSocieties"></education>
        </div>
    </div>
</template>

<script>

import Education from './Education.vue'

export default {
    name:'Educations',
    props:{
        educations : Array
    },
    methods:{
        addEducation(){
            this.$emit('add-edu',{
                degree : document.getElementById('degree').value,
                school: document.getElementById('university').value,
                field : document.getElementById('major').value,
                startYear : document.getElementById('eduStart').value,
                endYear : document.getElementById('eduEnd').value,
                grade : 4.0,
                activitiesSocieties: document.getElementById('summary').value,
            });
        }
    },
    components:{
        Education
    }
}
</script>