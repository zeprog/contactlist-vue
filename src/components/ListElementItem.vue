<template>
  <div>
    <div class="list-item">
      <div class="list-item__contact-info">
        <img src="../assets/contact-icon.png" alt="" width="40px" height="40px">
        <div class="list-item__info">
          <p class="list-item__name">{{ contact.name }}</p>
          <p class="list-item__phone">{{ contact.phone }}</p>
        </div>
      </div>
      <div class="list-item__delete" @click="openModal">
        <p>&#10006;</p>
      </div>
    </div>
    <hr />
    <DeleteModal v-show="active"
    @close="closeModal"
    @removeContact="removeContact"
    v-bind:contact="contact"/>
  </div>
</template>

<script>
import DeleteModal from '@/components/DeleteModalWindow.vue'

export default {
  name: 'ListItem',
  components: {
    DeleteModal
  },
  data () {
    return {
      active: false
    }
  },
  methods: {
    openModal () {
      this.active = true
    },
    closeModal () {
      this.active = false
    },
    removeContact (id) {
      this.$emit('removeContact', id)
      this.active = false
    }
  },
  props: ['contact']
}
</script>
