<template>
  <view :style="{flex:1}">
    <agenda
        v-bind:items="items"
        :loadItemsForMonth="loadItems"
        :selected= "{currentDate}"/>
  </view>
</template>

<script>
import {View,StyleSheet} from "react-native";
import {Agenda} from 'react-native-calendars';

const timeToString = (time) =>{
    var date = new Date(time);
    return date.toISOString().split('T')[0];
  };

export default {
  props: {
    navigation: { type: Object }
  },
  data: function() {
    return {
      currentDate: this.dateToString(new Date().toDateString().substring(4)),
      items: {}
    };
  },
  methods: {
    dateToString: function (time){
      var vm=this;
      var temp=time.split(" ");
      if (temp[0]=="Jan"){vm.currentDate="01";}
      else if (temp[0]=="Feb"){vm.currentDate="02";}
      else if (temp[0]=="Mar"){vm.currentDate="03";}
      else if (temp[0]=="Apr"){vm.currentDate="04";}
      else if (temp[0]=="May"){vm.currentDate="05";}
      else if (temp[0]=="Jun"){vm.currentDate="06";}
      else if (temp[0]=="Jul"){vm.currentDate="07";}
      else if (temp[0]=="Aug"){vm.currentDate="08";}
      else if (temp[0]=="Sep"){vm.currentDate="09";}
      else if (temp[0]=="Oct"){vm.currentDate="10";}
      else if (temp[0]=="Nov"){vm.currentDate="11";}
      else if (temp[0]=="Dec"){vm.currentDate="12";}
      if(temp[1].length<2){
        var t="0"+temp[1];
        vm.currentDate+="-";
        vm.currentDate+=t;
      }else{
        vm.currentDate+="-";
        vm.currentDate+=temp[1];
      }
      vm.currentDate+="-";
      vm.currentDate+=temp[2];
      
      return temp;
    },
    goToHomeScreen() {
      this.navigation.navigate("HomeScreen");
    },
    setItem(item){
      this.items=item;
    },
    loadItems(day){
      var vm =this;
      setTimeout(function() {
      for (let i = -15; i < 85; i++) {
        const time = day.timestamp + i * 24 * 60 * 60 * 1000;
        const strTime = timeToString(time);
        if (!vm.items[strTime]) {
          vm.items[strTime] = [];
          const numItems = Math.floor(Math.random() * 3 + 1);
          for (let j = 0; j < numItems; j++) {
            vm.items[strTime].push({
              name: 'Item for ' + strTime + ' #' + j,
              height: Math.max(50, Math.floor(Math.random() * 150))
            });
          }
        }
      }
      const newItems = {};
      Object.keys(vm.items).forEach(key => {
        newItems[key] = vm.items[key];
      });
      vm.setItem(newItems);
    }, 1000);
  }
  
  },
  components: {
    View, Agenda,StyleSheet, 
  }
};
</script>

<style>

</style>