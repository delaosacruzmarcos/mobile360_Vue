<template>
    <div class="row d-flex flex-column justify-content-start">
        <h5 class="text-left">Work experience
            <i class="fas fa-plus-circle" data-toggle="modal" data-target="#workModal"></i>
        </h5>
        
            <!-- Modal -->
            <div class="modal fade" id="workModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
                <div class="modal-dialog" role="document">
                    <div class="modal-content">
                        <div class="modal-header">
                            <h5 class="modal-title" id="exampleModalLabel">Work Experience</h5>
                            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                            </button>
                        </div>
                    <div class="modal-body text-left">
                        <form>
                            <div class="form-group">
                                <label for="company">Company</label>
                                <input type="text" class="form-control" id="company" placeholder="Company">
                            </div>
                            <div class="row">
                                <div class="col form-group">
                                    <label for="position">Position</label>
                                    <input type="text" class="form-control" id="position" placeholder="Position">
                                </div>
                                <div class="col form-group">
                                    <label for="type">Employment Type</label>
                                    <select class="form-control" id="type">
                                        <option value="">--Type--</option>
                                        <option value="Full-Time">Full-Time</option>
                                        <option value="Volunteer">Volunteer</option>
                                        <option value="Part-Time">Part-Time</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group">
                                <label for="location">Location</label>
                                <input type="text" class="form-control" id="location" placeholder="Location">
                            </div>
                            <div class="row">
                                <div class="col form-group">
                                    <label for="workstart">Start Date</label>
                                    <input type="date" class="form-control" id="workStart" placeholder="Company">
                                </div>
                                <div class="col form-group">
                                    <label for="workEnd">End Date</label>
                                    <input type="date" class="form-control" id="workEnd" placeholder="Company">
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label for="workSummary">Description</label>
                                <textarea class="form-control" id="workSummary"></textarea>
                            </div>
                            <div class="form-check">
                                <input type="checkbox" class="form-check-input" id="workCheck">
                                <label class="form-check-label" for="workCheck">Current Job?</label>
                            </div>
                            <button data-dismiss="modal" @click.prevent="addWork" type="submit" class="btn btn-primary">Add Experience</button>
                        </form>
                    </div>
                    </div>
                </div>
            </div>
            <div class="text-left" :key=index v-for="(experience,index) in workExperiences">
                <work class="m-1 p-2 rounded" style="background-color:#F5F5F5" :title="experience.title" :employment="experience.employment"
                    :company="experience.company" :location="experience.location"
                    :isCurrent="experience.isCurrent" :startDate="experience.startDate"
                    :endDate="experience.endDate" :description="experience.description"
                ></work>
            </div>
    </div>
</template>

<script>

import Work from './Work.vue';

export default {
    name: 'Works',
    props:{
        workExperiences : Array
    },
    methods:{
        addWork(){
            this.$emit('add-work', {
                title: document.getElementById('position').value,
                employment: document.getElementById('type').value,
                company: document.getElementById('company').value,
                location : document.getElementById('location').value,
                isCurrent : document.getElementById('workCheck').checked,
                startDate: document.getElementById('workStart').value,
                endDate: document.getElementById('workEnd').value,
                description : document.getElementById('workSummary').value
            })
        }
    },
    components:{
        Work
    }

}
</script>