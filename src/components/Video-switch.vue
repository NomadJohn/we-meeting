<template>
  <div class="switcher">
    <div class="switcher__audio">
      <span>开启麦克风</span>
      <el-switch :value="!state.muted" @change="val => setMuted(!val)"></el-switch>
    </div>
    <div class="switcher__video">
      <span>开启摄像头</span>
      <el-switch :value="!state.paused" @change="val => setPaused(!val)"></el-switch>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex';
export default {
  computed: {
    ...mapGetters({
      state: 'getState'
    })
  },
  methods: {
    ...mapMutations(['setMuted', 'setPaused'])
  }
};
</script>

<style lang="scss">
.switcher {
  display: inline-block;
  margin-left: 50%;
  transform: translateX(-50%);
  white-space: nowrap;
  margin-top: 10px;
  &__audio {
    margin-right: 10px;
  }
  &__audio,
  &__video {
    span {
      margin-right: 3px;
    }
    display: inline-block;
    color: #627e9a;
    background: #f7f5f5;
    border-radius: 13px;
    padding: 5px 7px;
  }
}
</style>