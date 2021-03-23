<template>
  <div>
    <div
      id="on"
      @click="switched(true)"
      :class="{active: value}"
    >Blue</div>
    <div
      id="off"
      @click="switched(false)"
      :class="{active: !value}"
    >Red</div>
  </div>
</template>

<script>
export default {
  props: ['value'],
  methods: {
    switched (isOn) {
      this.$emit('input', isOn)
    }
  }
}
</script>

<style scoped>
#on,
#off {
  width: 40px;
  height: 20px;
  background-color: black;
  color: white;
  padding: 2px;
  display: inline-block;
  margin: 10px -2px;
  box-sizing: content-box;
  cursor: pointer;
  text-align: center;
}

#off:hover {
    background-color: #EF6351;
    transition: .5s;
    left: 0;
}

#off.active {
  background-color: #F38375;
}

#on:hover{
    background-color: #788Bff;
    transition: .5s;
    left: 0;
}

#on.active {
  background-color: #5465FF;
}
</style>