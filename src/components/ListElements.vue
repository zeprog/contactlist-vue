<template>
  <div class="content__list-item">
    <ListItem v-for="(contact, idx) of contacts"
    :key="idx"
    v-bind:contact="contact"
    @removeContact="removeContact"/>
  </div>
</template>

<script>
import ListItem from '@/components/ListElementItem.vue'

export default {
  name: 'ListElement',
  components: {
    ListItem
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
  props: ['contacts']
}
</script>

<style lang="scss">
$lightGrayColor: #eee;

.content__list-item {
  cursor: pointer;

  .list-item {
    display: flex;
    justify-content: space-between;
    padding: 10px 0;
    &:hover {
      background-color: $lightGrayColor;
    }

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
