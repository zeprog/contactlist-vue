<template>
  <div class="list">
    <Header />
    <Content @addContact="addContact"/>
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
  },
  methods: {
    addContact () {
      this.$emit('addContact')
    }
  }
}
</script>
