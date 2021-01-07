<template>
  <div class="header">
    <div class="header-body">
      <h1 class="header__title">МоиКонтакты</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss">
$mainColor: #00BFFF;
$whiteColor: #fff;

.header {
  height: 50px;
  background-color: $mainColor;
  display: flex;
  align-items: center;

  .header-body {
    width: 1000px;
    margin: 0 auto;

    .header__title {
    color: $whiteColor;
    font-size: 28px;
    text-transform: uppercase;
    cursor: pointer;
    }
  }
}
</style>
