<template>
  <div class="container-fluid">
    <div class="row text-left">
      <div class="col-3 col-lg-3 col-md-3 col-sm-3">
        <div class="card">
          <div class="card-header">
            <i class="fas fa-user-cog"></i>
            Younnnections Manager 
          </div>
          <div class="card-body manager">
            <div :key="index" v-for="(manage,index) in manager">
              <div class="row text-left">
                <div class="col-1">
                  <i :class="manage.logo"></i>
                </div>
                <div class="col-7">
                  <p class="text-left"> {{manage.type}}</p>
                </div>
                <div class="col-3 justify-content-end">
                  <p class="text-right">{{manage.count}}</p>
                </div>
              </div>
              <hr>
            </div>
          </div>
          <div class="card-footer text-muted">
          </div>
        </div>
      </div>
      <div class="col-6 col-lg-6 col-md-6 col-sm-6">
        <div class="card text-left">
          <div class="card-header">
            Requests from younnectors
          </div>
          <div class="card-body">
            <ul class="list-group">
              <li class="list-group-item" :key="index" v-for="(req,index) in requests">
                <div class="row">
                  <div class="col-6">
                    <p>{{req.name}}</p>
                    <small>{{req.summary}}</small>
                  </div>
                  <div class="col-6 text-right">
                    <div class="row justify-content-center">
                      <button class="col btn btn-sm btn-outline-success" @click="accept(index)">Younnect</button>
                      <button class="col btn btn-sm btn-outline-success" @click="reject(index)">Youject</button>
                    </div>
                  </div>
                </div>
              </li>
            </ul>
          </div>
          <div class="card-footer text-muted">
            <!-- 2 days ago -->
          </div>
        </div>
      </div>
      <div class="col-3 col-lg-3 col-md-3 col-sm-3">
        <div class="card text-left">
            <div class="card-body">
                <h5 class="card-title">Your ad goes here</h5>
                <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                <a href="#" class="card-link">Ad link</a>
            </div>
            <hr>
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
</template>

<script>
export default {
  name : 'Younnections.vue',
  methods:{
    accept(index){
      this.manager[0].count+=1;
      this.requests.splice(index,1);
    },
    reject(index){
      console.log(index)
      this.requests.splice(index,1);
    }
  },
  data(){
    return{
      requests : [{
        name : 'Chin Ya Russell',
        summary : 'Administrative Assistant at Atwick.Inc'
      },
      {
        name : 'Shivaleela Hubli',
        summary : 'Gradute Student at UB'
      },
      {
        name : 'Jeff Bezos',
        summary : 'CEO at Amazon'
      },
      {
        name : 'Elon Musk',
        summary : 'Founder/CEO at Tesla, PayPal, SpaceX'
      },
      {
        name : 'Sathish Thripati',
        summary : 'President at University at Buffalo'
      },
      {
        name : 'Steve Jobs',
        summary : 'Founder, Pixar'
      }],
      manager : [{
          type : 'Connections',
          count : 101,
          logo : 'fas fa-people-arrows'
      },
      {
          type : 'Groups',
          count : 10,
          logo: 'fas fa-users'
      },
      {
          type : 'Pages',
          count : 99,
          logo : 'far fa-file'
      },
      {
          type : 'Contacts',
          count : 165,
          logo : 'far fa-address-book'
      },
      {
          type : 'People',
          count : 17,
          logo : 'fas fa-user-plus'
      }]
    }
  }
}
</script>

<style scoped>

p{
  margin :0;
}

h6{
  display: inline;
}

.manager p{
  display: inline;
}

.list-group{
    max-height: 50vh;
    margin-bottom: 10px;
    overflow-y:auto;
    -webkit-overflow-scrolling: touch;
}
</style>
