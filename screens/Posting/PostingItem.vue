<template>
    <view class='posting-wrapper'>
        <touchable-opacity :on-press='handleTaskPressed' v-if="!post.edited">
            <text v-bind: class="[post.isLiked ? 'text-post-liked' : 'text-posting-task]">
                {{post.task}}
            </text>
        </touchable-opacity>
        <view class="posting-input-wrapper" v-if="post.edited">
            <text-input aria-placeholder="Enter post info" v-model='editedPost'/>
        </view>
        <view class='post-button-wrapper' v-if="post.edited">
            <!-- these are the two images that are added to the postings -->
            <touchable-opacity :on-press="CheckIconPress" class='done-button'>
                <!-- Insert the Check icon image here <image : source='image_name' class='image-style'/> -->
            </touchable-opacity>
            <touchable-opacity v-bind:on-press="CancelIconPress" class='done-button'>
                <!-- same approach with the source code -->
        </view>
        <view class='post-button-wrapper' v-if="!post.edited">
            <touchable-opacity :on-press="editIconPress" class='edit-button'>
                <!-- same approabut with edit button image -->
            </touchable-opacity>
            <touchable-opacity :on-press="deleteIconPress">
               <!-- same -->
            </touchable-opacity>
        </view>
    </view>                                    
</template>

<script>

export default {
    data: function() {
        return {
            editedPost: this.post.apply,
            editIcon,
            crossIcon,
            checkIcon
        };
    },
 props: {
     post: Object,
     selectedIndex: Number,
     editPost: Function,
     deletePost: Function,
     cancelEdit: Function,
     toggleLikedStatus: Function,
     editPressed: Function
 },
 methods: {
     editIconPress: function() {
         this.editPressed(this.selectedIndex)
     },
     checkIconPress: function() {
         if(this.editedPost !== '')
           this.editPost(this.selectedIndex, this.editedPost)
         else {
             this.editedPost = this.post.data
             this.cancelEdit(this.selectedIndex)
         }  
     },
     cancelIconPress: function(){
         this.cancelEdit(this.selectedIndex)
     },
     handleTaskPressed: function() {
         this.toggleLikedStatus(this.selectedIndex)
     },
     deleteIconPress: function(index) {
         this.deletePost(this.selectedIndex)
     },
    }
}

</script>

 
<style>
.post-button-wrapper {
  flex-direction: row
}
.done-button {
  margin-left: 20
}
.image-style {
  height: 20;
  width: 20;
}
.edit-button {
  padding-right: 20
}
.text-post-task {
  color:grey;
}
.text-task-completed {
  color: rgba(201, 29, 29, 0.534);
  text-decoration-line: line-through;
}
.posting-input-wrapper {
  flex: 1;
  border-width: 1;
  border-color: rgba(201, 29, 29, 0.534);
  justify-content: center;
  padding: 10
}
.todo-wrapper {
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
  flex: 1;
}
</style>
