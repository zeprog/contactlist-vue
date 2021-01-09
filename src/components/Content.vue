<template>
  <div>
    <div class="content">
      <div class="content__body">
        <p class="content__text">Все контакты</p>
        <hr />
        <ListElement v-bind:contacts="contacts"
        @removeContact="removeContact"
        v-if="contacts.length"/>
        <p class="content__text-nocontact" v-else>У вас нет ни одного контакта</p>
        <AddModal v-show="active"
        @addContact="addContact"
        @close="close"/>
      </div>
    </div>
    <AddContactButton @openModal="open"/>
  </div>
</template>

<script>
import ListElement from '@/components/ListElements.vue'
import AddModal from '@/components/AddModalWindow.vue'
import AddContactButton from '@/components/AddContactButton.vue'

export default {
  name: 'Content',
  components: {
    ListElement, AddModal, AddContactButton
  },
  data () {
    return {
      contacts: [
        { id: 1, name: 'Name', phone: '+' + 79242874764 },
        { id: 2, name: 'Name', phone: '+' + 79242874764 }
      ],
      active: false
    }
  },
  methods: {
    removeContact (id) {
      this.contacts = this.contacts.filter(c => c.id !== id)
    },
    addContact (newContact) {
      this.contacts.push(newContact)
      this.active = false
    },
    close () {
      this.active = false
    },
    open () {
      this.active = true
    }
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

    .content__text-nocontact {
      font-size: 16px;
      opacity: .6;
      padding-top: 10px;
      text-align: center;
    }
  }
}

hr {
  opacity: .4;
  margin: 0;
}
</style>
