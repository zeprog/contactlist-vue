<template>
  <div class="add-button">
    <div class="add-button__body">
      <p>+</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddContactButton'
}
</script>

<style lang="scss">
$mainColor: #00BFFF;
$hoverColor: #20c7ff;

.add-button {
  display: fixed;
  position: absolute;
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
