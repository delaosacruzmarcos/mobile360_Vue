<template>
  <touchable-opacity :on-press="openDrawer">
    <image class="icon" :source="require('../assets/menu-icon.png')" />
  </touchable-opacity>
</template>

<script>
import { Alert } from 'react-native';
export default {
  props: {
    navigation: { type: Object },
  },
  data() {
    return {};
  },
  methods: {
    openDrawer: function() {
      this.$emit("drawer");
    },
  },
};
</script>

<style>
.icon {
  width: 35px;
  height: 35px;
  margin-top: 5%;
}
</style>
