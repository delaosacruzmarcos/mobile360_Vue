<template>
<view class="main-container">
    <view class="manager-container">
        <view class="header-container">
            <image class="icon"
            :source="require('../assets/manager.png')"
        />
            <text class="header">Younnections Manager</text>
        </view>
        <touchable-opacity class="sections">
            <text class="manger-text">Connections</text>
            <text class="manger-text">101</text>
        </touchable-opacity>
        <touchable-opacity class="sections">
            <text class="manger-text">Groups</text>
            <text class="manger-text">10</text>
        </touchable-opacity>
        <touchable-opacity class="sections">
            <text class="manger-text">Contacts</text>
            <text class="manger-text">165</text>
        </touchable-opacity>
    </view>
    <view class="request-container">
        <view class="header-container">
            <image class="icon"
            :source="require('../assets/request-friend.png')"
        />
            <text class="header">Requests from younnectors</text>
        </view>
        <view class="request">
            <view class="person">
                <text class="request-person">Chin Ya Russell</text>
                <text class="request-info">Administrative Assistant at Atwick.Inc</text>
            </view>
            <view class="btns">
                <touchable-opacity class="accept"><text class="accept-text">Younnect</text></touchable-opacity>
                <touchable-opacity class="reject"> <text class="reject-text">Youject</text></touchable-opacity>
            </view>
        </view>
        <view class="request">
            <view class="person">
                <text class="request-person">Shivaleela Hubli</text>
                <text class="request-info">Graduate Student at UB</text>
            </view>
            <view class="btns">
                <touchable-opacity class="accept"><text class="accept-text">Younnect</text></touchable-opacity>
                <touchable-opacity class="reject"> <text class="reject-text">Youject</text></touchable-opacity>
            </view>
        </view>
    </view>
</view>
</template>

<script>

export default {
  data() {
    return {
      
    };
  },
  methods: {
  },
  components:{
  }
};
</script>

<style>
.main-container{
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: white;
}
.manager-container{
    height: 25%;
    width: 90%;
    margin-top: 4%;
}
.request-container{
    height: 65%;
    width: 90%;
    margin-top: 4%;
}

.header-container{
    height: 45;
    background-color: #d9f2e6;
    justify-content: flex-start;
    flex-direction: row;
    align-items: center;
}
.header{
    font-size: 16px;
    color:black;
    font-weight: bold;
}
.icon{
    width: 35px;
    height: 35px;
    margin: 15px;
}
.sections{
    background-color: white;
    flex-direction: row;
    justify-content: space-between;
    border-bottom-width: 1;
    border-bottom-color: #d9d9d9;
}
.manger-text{
    padding: 8;
    font-size: 15px;
    color:black;
}
.request{
    flex-direction: row;
    justify-content: space-between;
    border-bottom-width: 1;
    border-bottom-color: #d9d9d9;
    margin-bottom: 5px;
}
.person{
    margin:10px;
    flex-direction: column;
}
.btns{
    flex-direction: row;
    align-items: center;
    justify-content: space-around;
    width: 35%;
}
.request-person{
    font-size: 15px;
    font-weight: bold;
    padding-bottom: 5px;
}
.request-info{
    font-size: 10px;
}
.accept{
    /* border-bottom-width: 1;
    border-bottom-color: green;
    border-top-width: 1;
    border-top-color: green;
    border-left-width: 1;
    border-left-color: green;
    border-right-width: 1;
    border-right-color: green; */
    background-color: green;
    border-radius: 5px;
}
.accept-text{
    color: white;
    font-size: 14px;
    padding: 4px;
}
.reject{
    background-color: red;
    border-radius: 5px;
}
.reject-text{
    color: white;
    font-size: 14px;
    padding: 4px;
}
</style>