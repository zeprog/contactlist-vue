<template>
  <div class="list">
    <Header />
    <Content />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Content from '@/components/Content.vue'

export default {
  name: 'ContactList',
  components: {
    Header,
    Content
  }
}
</script>
