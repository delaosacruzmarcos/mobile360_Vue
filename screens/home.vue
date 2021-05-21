<template>
<!-- we are currently applying the home screen from the components folder, not this one -->
<!-- header here -->
<view>
    <header>
        <nb-container :style="{ backgroundColor: '#fff' }">
    <nb-header>
      :style="{ backgroundColor: green"
      <nb-left>
        <nb-button transparent :onPress="() => this.props.navigation.goBack()">
          <nb-icon name="arrow-back" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>App360</nb-title>
      </nb-body>
      <nb-right>
        <nb-button transparent>
          <nb-icon name="search" />
        </nb-button>
        <nb-button transparent>
          <nb-icon name="ellipsis-vertical" />
        </nb-button>
      </nb-right>
    </nb-header>
    <nb-content padder>
      <nb-text>Header with multiple Icon Buttons</nb-text>
    </nb-content>
  </nb-container> 
    </header>
</view>
<view>
<image-background :source="require('../assets/background.png')" class="background">
        <image class="avatar"
            :source="require('../assets/icons8-user-male-500.png')"
        />
        <view class="info">
            <text class="info-text-name">Bhargav Koritala</text>
            <text class="info-text">bhargavK@example.com</text>
        </view>
        <text class="about-content">Hard-working individual with proficiency in HTML, JavaScript, and CSS, as well as ability to communicate effectively in a team setting.</text>
    </image-background> 
</view>
<add-post
        :on-add='addPost'
 />       
 <scroll-view :content-container-style="{contentContainer: {
     paddingVertical: 20
     }}">
     <view class="posting-wrapper" v-for='(posting,index) in posting' :key='index'>
         <posting-item
         :post='post'
         :selected-index='index'
         :edit-pressed='onEditPressed'
         :edit-post='editPost'
         :delete-post='editPost'
         :cancel-edit='cancelEdit'
         :toggle-liked-status='toggleLikedStatus'
         />
     </view>         
 </scroll-view> 
 <!-- the footer goes here -->  
<view>
    <footer>
        <b-textarea> Yolo no footer here </b-textarea>
    </footer>
</template>

<script>
// I just copied and pasted the header and the footer in, can solve the impoer issue later 
// import NewContent from '../components/NewContent.vue'
// import Header from './header/HeaderWithButtons.vue'
// import Footer from './footer/iconFooter'

import PostingItem from "./Posting/PostingItem"
import AddPost from "./Posting/AddPost"
// import AddPost from './Posting/AddPost.vue'
// import PostingItem from './Posting/PostingItem.vue'
export default {
  data: function() {
      return {
          newPost: '',
          posts:[]
      };
  },
  components: {
      AddPost,
      PostingItem
  },
  methods: {
      AddPost: function(post){
          this.posts.push(post)
      },
      onEditPressed: function(index){
          this.posts[index].edited = true
      },
      cancelEdit: function(index){
          this.posts[index].edited = false
      },
      toggleLikedStatus: function(index) {
          this.posts[index].isLiked = !this.posts[index].isLiked
      },

  }
}
</script>

<style scoped>
.container {
    background: blanchedalmond;
    flex: 1;
    padding-top: 40;
}
.posting-wrapper {
    background: forestgreen;
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
    padding: 10;
    border-radius: 5;
}
</style>