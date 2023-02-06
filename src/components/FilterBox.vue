<template>
  <div @click="fire" :class="filter + ' filter-item'" :style="`background-image:url(${image})`">
    <slot></slot>
    </div> 
</template>

<script>
export default {
  name : 'filterbox',
  methods : {
    fire(){
      this.emitter.emit('clickBox',this.filter);
    }
  },
  props : {
    image : String,
    filter : String,
  }
}
</script>

<style>
  .filter-item {
  width: 100px;
  height: 100px;
  margin: 10px 10px 10px auto;
  padding: 8px;
  display: inline-block;
  color : black;
  background-size: cover;
  background-position : center;
}
</style>