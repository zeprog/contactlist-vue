<template>
  <div class="content__list-item">
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
  name: 'ListElement',
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
      console.log(this.active)
    },
    removeContact (id) {
      this.$emit('removeContact', id)
    }
  },
  props: ['contact']
}
</script>

<style lang="scss">
$lightGrayColor: #eee;

.content__list-item {
  cursor: pointer;
  &:hover {
    background-color: $lightGrayColor;
  }

  .list-item {
    display: flex;
    justify-content: space-between;
    padding: 10px 0;

    .list-item__contact-info {
      display: flex;

      .list-item__info {
      padding-left: 15px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;

        .list-item__name {
          font-size: 16px;
        }

        .list-item__phone {
          font-size: 14px;
          opacity: .6;
        }
      }
    }

    .list-item__delete {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding-right: 15px;
      opacity: .6;
      cursor: pointer;
    }
  }
}
</style>
