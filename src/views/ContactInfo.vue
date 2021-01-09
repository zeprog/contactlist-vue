<template>
  <div class="contact-info">
    <Header />
    <ContentInfo />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import ContentInfo from '@/components/ContentForInfo.vue'

export default {
  name: 'ContactInfo',
  components: {
    Header, ContentInfo
  }
}
</script>
