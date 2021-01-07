<template>
  <div class="content">
    <div class="content__body">
      <p class="content__text">Все контакты</p>
      <hr />
      <ListElement />
      <ListElement />
    </div>
  </div>
</template>

<script>
import ListElement from '@/components/ListElements.vue'

export default {
  name: 'Content',
  components: {
    ListElement
  }
}
</script>

<style lang="scss">
.content {
  width: 1000px;
  margin: 0 auto;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-top: 10px;

  .content__body {
    padding: 15px 15px;

    .content__text {
    font-size: 16px;
    opacity: .6;
    padding-bottom: 10px;
    }
  }
}

hr {
  opacity: .4;
  margin: 0;
}
</style>
