<template>
  <div class="add-button">
    <div class="add-button__body" @click="open">
      <p>+</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddContactButton',
  components: {},
  data () {
    return {
      active: false
    }
  },
  methods: {
    open () {
      this.$emit('openModal')
    }
  }
}
</script>

<style lang="scss">
$mainColor: #00BFFF;
$hoverColor: #20c7ff;

.add-button {
  display: block;
  position: fixed;
  top: 88%;
  left: 94%;

  .add-button__body {
    width: 60px;
    height: 60px;
    background-color: $mainColor;
    border-radius: 50%;
    cursor: pointer;

    &:hover {
      background-color: $hoverColor;
    }

    p {
      color: #fff;
      text-align: center;
      font-size: 42px;
      line-height: 60px;
    }
  }
}
</style>
