<template>
  <View class="home">
    <view class="m-2 row">
      <view class="col-lg-3">
        <view class="card">
            <view class="card-header">
              <router-link to="/profile">Sri Sai Bhargav Koritala</router-link>
            </view>
          </view>
        <view id="accordion">
          <view class="card">
            <view class="card-header" id="headingOne">
              <h5 class="mb-0">
                <button
                  title = "Profile"
                  accesskey="Profile"
                  :on-press = "Profile"
                />
              </h5>
            </view>

            <view id="collapseOne" class="collapse show" aria-labelledby="headingOne" data-parent="#accordion">
              <view class="card-body">
                <strong>Sri Sai Bhargav Koritala</strong>
                <p><small>Master's in Computer Science at University at Buffalo.</small></p>
              </view>
            </view>
          </view>
          <view class="card">
            <view class="card-header" id="headingTwo">
              <h5 class="mb-0">
                <button> 
                  title = "Groups"
                />
              </h5>
            </view>
            <view id="collapseTwo" class="collapse" aria-labelledby="headingTwo" data-parent="#accordion">
              <view class="card-body">
                <view :key="index" v-for="(group,index) in groups">
                  <view class="row text-left">
                    <view class="col">
                      <p class="groups text-left"> {{group}}</p>
                    </view>
                  </view>
                  <hr>
                </view>
              </view>
            </view>
          </view>
          <view class="card">
            <view class="card-header" id="headingThree">
              <h5 class="mb-0">
                <button class="btn btn-link collapsed" data-toggle="collapse" data-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
                  tittle = "Widgets"
                </button>
              </h5>
            </view>
            <view id="collapseThree" class="collapse" aria-labelledby="headingThree" data-parent="#accordion">
              <view class="wid card-body row justify-content-between" :key="index" v-for="(widget,index) in widgets">
                <div class="col">
                  <small class="text-left">{{widget}}</small>
                </div>
                <div class="col">
                  <i class="fas fa-plus-circle" data-toggle="modal" data-target="#workModal"></i>
                </div>
                
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-6">
        <NewContent class="indiBorder mb-2"/>
        <div class="container">
          <div style="background:white" :key="index" v-for="(post,index) in posts" class="row mb-2 rounded justify-content-center">
          <div class="col-12 indiBorder rounded text-left p-2">
              <div class="row justify-content-start">
                <div class="col-1 mx-2">
                  <img class="border rounded border-success" height=50 width=50 src="../assets/pp.png" alt="profile_pic">
                </div>
                <div class="col">
                  <h6>{{post.user}}</h6>
                  <small>{{post.profile}}</small>  
                </div>
              </div>
            <small>{{post.content}}</small>
            <br>
            <div v-if="post.urls.length!=0">
              <small><a target="_blank" :href="url" :key="index" v-for="(url, index) in post.urls">{{url}}</a></small>
            </div>
            <small :key="index" v-for="(hash, index) in post.hashtags">#{{hash}}</small>
            <hr>
            <div class="input-group input-group-sm">
              <input type="text" class="form-control" placeholder="Comment">
              <div class="input-group-append">
                <button class="btn btn-outline-secondary" type="button"><i class="far fa-paper-plane"></i></button>
              </div>
            </div>
          </div>
        </div>
        </div>
      </div>
      <!-- <div class="col-lg-3">
        <div class="row d-flex flex-column">
          <div class="col card text-left mb-2">
            <div class="card-body">
                <h5 class="card-title">Your ad goes here</h5>
                <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                <a href="#" class="card-link">Ad link</a>
            </div>
          </div>
          <div class="col card text-left">
            <div class="card-body">
                <h5 class="card-title">Your ad goes here</h5>
                <h6 class="card-subtitle mb-2 text-muted">Ad subtitle</h6>
                <p class="card-text">Ad content to reach better audience and promote your thoughts and ideas.</p>
                <a href="#" class="card-link">Ad link</a>
            </div>
          </div>
        </div> -->
      <!-- </div> -->
    </view>  
  </View>
</template>

<script>
// @ is an alias to /src
import NewContent from '@/components/NewContent.vue'
export default {
  name: 'Home',
  components: {
    NewContent
  },
  data(){
    return{
      groups:['Atwick Employees', 'Atwick Developers', 'UB CSE'],
      widgets : ['Calendar', 'Payment', 'Video Meeting', 'E-Commerce'],
      posts : [{
        user : 'Shivaleela Hubli',
        profile : 'Graduate Student at UB',
        content : 'Looking for Full-Stack developer roles',
        urls : [], 
        hashtags : ['opentowork','fullstackroles','jobsearch']
      },
      {
        user : 'Chin Ya Russell',
        profile : 'Administrative Assistant at Atwick Inc.',
        content : 'Atwick Inc is hiring for the role of Full Stack Developer! Apply through the given link',
        urls : ['https://atwick.com/fullstackdeveloper'],
        hashtags : ['atwick','fullstackroles','hiring']
      },
      {
        user : 'Atwick Inc',
        profile : '100,100 followers',
        content : 'We are hiring! Apply through the link to work with us!!',
        urls : ['https://atwick.com/fullstackdeveloper'],
        hashtags : ['atwick','fullstackroles','hiring']
      }]
    }
  }
}
</script>

<style scoped>

p.groups{
  cursor:pointer;
}

.wid div{
  margin: 0;
  padding: 0;
   float: left;
}

h6{
  margin:0;
}

</style>
