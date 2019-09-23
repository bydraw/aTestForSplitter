<template>
  <div id="app">
    <span>normal component √</span>
    <div id="test1">
      <test></test>
    </div>
    <!--  -->
    <span>splitter only √</span>
    <div id="test2">
      <vue-splitter-v>
        <template slot="left">content...</template>
        <template slot="right">content...</template>
      </vue-splitter-v>
    </div>
    <!--  -->
    <span>nested component in splitter's template slot X</span>
    <div id="test3">
      <vue-splitter-v>
        <template slot="left">
          <test></test>
        </template>
        <template slot="right">content...</template>
      </vue-splitter-v>
    </div>
    <!--  -->
    <span>even splitter component itself in template X</span>
    <div id="test4">
      <vue-splitter-v>
        <template slot="left">
          <vue-splitter-v>
            <template slot="left">content...</template>
            <template slot="right">content...</template>
          </vue-splitter-v>
        </template>
        <template slot="right">content...</template>
      </vue-splitter-v>
    </div>
    <!--  -->
    <br />
    <br />
    <i>But They all perform well in umd/cdn mode.</i>
  </div>
</template>

<script>
import Vue from 'vue'
import { VueSplitterV } from 'vue-splitter-pane'

const test = {
  template: '<div>This is a custom component.</div>'
}
Vue.component('test', test)

export default {
  name: 'App',
  components: {
    VueSplitterV
  }
}
</script>

<style>
#app > div {
  height: 100px;
  background-color: #ddd;
  margin-bottom: 15px;
}
#app span {
  font-weight: bold;
}
</style>
