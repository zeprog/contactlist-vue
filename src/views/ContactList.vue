<template>
  <div class="list">
    <Header />
    <Content />
    <AddContactButton />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Content from '@/components/Content.vue'
import AddContactButton from '@/components/AddContactButton.vue'

export default {
  name: 'ContactList',
  components: {
    Header,
    Content,
    AddContactButton
  }
}
</script>
