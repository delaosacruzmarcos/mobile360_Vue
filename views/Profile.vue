<template>
    <div class="container-fluid">
        <div class="jumbotron indiBorder bg-white p-2 justify-content-around">
            <div class="row">
                <div class="col-3 ">
                <div class="row">
                    <div class="col-1 icon-bar d-flex flex-column my-2">
                        <a href="#" class="facebook py-1"><i class="fab fa-facebook-square"></i></a>
                        <a href="#" class="twitter py-1"><i class="fab fa-twitter-square"></i></a>
                        <a href="#" class="google py-1"><i class="fab fa-google"></i></a>
                        <a href="#" class="linkedin py-1"><i class="fab fa-linkedin"></i></a>
                    </div>
                    <div class="col-10  text-right">
                        <img class="indiBorder rounded-circle bg-success" src="../assets/pp.png" alt="profile_pic">
                    </div>
                </div>
            </div>
            <div class="col-9 text-left">
                <h4><strong class="mb-3">Bhargav Koritala</strong></h4>
                <p class="intro mt-2"><small>{{intro}}</small></p>
                <hr>
                <div class="indiBorder bg-light rounded p-2">
                    <h6 class="lead">About</h6>
                    <p class="profileSummary">{{profileSummary}}</p>
                </div>
            </div>
            </div>
        </div>
        <hr>
        <div class="row justify-content-around m-3">
            <div class="col-8">
                <div class="row d-flex flex-column justify-content-start">
                    <h5 class="text-left">Featured</h5>
                    <img height=50 width=50 src="../assets/pp.png" alt="profile_pic">
                </div>
                <hr class="segment">
                <app-education @add-edu='addEdu' :educations="qualifications"></app-education>
                <hr class="segment">
                <app-work @add-work="addWork" :workExperiences="experiences"></app-work>
                <hr class="segment">
                <div class="row d-flex flex-column justify-content-start">
                    <h5 class="text-left">
                        Skills
                        <i class="fas fa-plus-circle" data-toggle="modal" data-target="#skillModal"></i>
                    </h5>
                    <div class="modal fade" id="skillModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
                        <div class="modal-dialog" role="document">
                            <div class="modal-content">
                                <div class="modal-header">
                                    <h5 class="modal-title" id="exampleModalLabel">Skills</h5>
                                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                                    <span aria-hidden="true">&times;</span>
                                    </button>
                                </div>
                            <div class="modal-body text-left">
                                <form>
                                    <div class="input-group my-2">
                                        <label class="input-group-text" for="newSkill">Skill</label>
                                        <input aria-describedby="skillHelp" class="form-control" type="text" name="" id="newSkill">
                                    </div>
                                    <small id="skillHelp" class="mb-2 form-text text-muted">Add multiple skills sperated by 'comma'</small>
                                    <button data-dismiss="modal" @click.prevent="addSkill" type="submit" class="btn btn-primary">Add Skill</button>
                                </form>
                            </div>
                    </div>
                </div>
            </div>
                    <div class="d-flex justify-content-start">
                        <div class="talent border bg-success text-white p-1 mx-1" :key="index" v-for="(skill,index) in skills">
                            {{skill}}
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-3 text-left">
                <div class="row d-flex flex-column">
                    <div class="row"><h6 class="col text-left">Promoted</h6></div>
                        <div class="row">
                            <div class="col">
                                <div class="card">
                                    <div class="card-body">
                                        <h5 class="card-title">Your ad goes here</h5>
                                        <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                                        <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                                        <a href="#" class="card-link">Ad link</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                <hr class="segment">
                <div class="row justify-content-start">
                    <h5 class="text-left">People you may know</h5>
                    <div class="col-12" :key="index" v-for="(recommendedPerson,index) in recommendedPeople">
                        <div class="row indiBorder rounded mb-1 bg-white">
                            <div class="col-3">
                                <img height=70 width=70 src="../assets/pp.png" alt="profile_pic">
                            </div>
                            <div class="col-9">
                                <small>{{recommendedPerson.name}}</small>
                                <p> <small>{{recommendedPerson.intro}}</small></p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import Work from '../components/Work/Works.vue'
import Education from '../components/Education/Educations.vue'
export default {
    name:'Profile',
    components: {
        appWork:Work,
        appEducation:Education
    },
    methods:{
        addSkill(){
            var newSkills = document.getElementById('newSkill').value.split(',')
            console.log(newSkills)
            newSkills.forEach(element => {
                this.skills.push(element)
            });
            document.getElementById('newSkill').value='';
        },
        addEdu(newEdu){
            console.log(newEdu)
            this.qualifications.push(newEdu);
        },
        addWork(newWork){
            console.log(newWork)
            this.experiences.push(newWork);
        }
    },
    data(){
        return{
            qualifications:[{
                degree :"Master's",
                school:'University at Buffalo',
                field : 'Computer Science',
                startYear : 2019,
                endYear : 'Present',
                grade : '4.0',
                activitiesSocieties: 'UB Hacking 2020'
            },
            {
                degree :"Bachelor's",
                school:'Vellore Institute of Technology',
                field : 'Electronics and Communication',
                startYear : 2013,
                endYear : '2017',
                grade : '8.28',
                activitiesSocieties: 'Design Head at SEDS VIT'
            }],
            experiences:[{
                title: 'Full Stack Developer Intern',
                employment: 'Intern',
                company: 'Atwick Inc.',
                location : 'Ithaca,NY',
                isCurrent : true,
                startDate: '2020-10-12',
                endDate: 'Present',
                description : 'Collaborating with management, departments and customers to identify end-user requirements and specifications. Designing algorithms and flowcharts to create new software programs and systems.Producing efficient and elegant code based on requirements'
            },
            {
                title: 'Software Developer',
                employment: 'Full-Time',
                company: 'Infosys Ltd.',
                location : 'Bangalore,India',
                isCurrent : false,
                startDate: '2017-06-12',
                endDate: '2019-07-08',
                description : 'Creative and people-oriented Computer Scientist with extensive project management experience. Advanced knowledge of the creation of graphic design software and programming languages relevant to the web.'
            }],
            skills:['HTML','CSS','JavaScript', 'VueJS', 'NodeJS', 'ExpressJS', 'MongoDB'],
            profileSummary: 'A person of keen interest in learning and gaining knowledge over domains spanning from Technology to Teaching. A strong believer of adaptability and innovation. ',
            recommendedPeople: [{
                name: 'Shivaleela Hubli',
                intro: 'SDE Intern at Atwick Inc.'
            },
            {
                name: 'Chin Ya Russell',
                intro: 'SDE Intern at Atwick Inc.'
            },
            {
                name: 'Elon Musk',
                intro: 'SDE Intern at Atwick Inc.'
            },
            {
                name: 'Steve Jobs',
                intro: 'SDE Intern at Atwick Inc.'
            },
            {
                name: 'Jeff Bezos',
                intro: 'SDE Intern at Atwick Inc.'
            }],
            intro: 'Computer Science Graduate at University at Buffalo'
        }
    }
}
</script>

<style scoped>

.talent{
    border-radius: 5vh;
}

hr.segment{
    border: 1px solid green;
}

i.fas.fa-edit{
    cursor: pointer;
}

.dp{
    border: 5px dotted green;
    border-radius: 100%;
}

.icon-bar{
    font-size: 4vh;
}

.facebook {
  color: #3B5998;
}

.twitter {
  color: #55ACEE;
}

.google {
  color: #dd4b39;
}

.linkedin {
  color: #007bb5;
}

.dash{
    border-right: 1px solid green;
}

.profileSummary{
    position: relative;
    bottom: 0;
    margin: 0;
}
</style>