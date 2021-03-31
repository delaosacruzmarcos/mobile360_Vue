<template>
    <view class= "text-input-container">
     <view class="text-input-wrapper">
         <text-input aria-placeholder="What would you like to share?" v-model="newPost"/>
     </view>
     <touchable-opacity class="add-button" title="Button" :on-press="addPost" :disabled="(newPost === '')">
         <text class="text-color-primary">ADD</text>
     </touchable-opacity>
     </view>    
</template>

<script>
export default {
    data: function() {
        return{
            newPost: ''
        };
    },
    props: {
        onAdd: Function
    },
    methods: {
        addPost: function() {
            let post = {
                comment: this.newPost,
                isLiked: false,
                edited: false
            }
            this.onAdd(post)
            this.newPost = ''
        },
    }
}
</script>

<style scoped>
.text-color-primary {
    color: white
}
.text-input-wrapper {
    flex: 1;
    border-width: 1;
    border-color: yellow;
    justify-content: center;
    padding: 10;
}
.add-button {
    background-color:white;
    justify-content: center;
}
.text-input-container {
    flex-direction: row;
    padding-bottom: 20
}
</style>