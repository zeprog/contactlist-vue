<template>
  <div>
    <div class="modal__background" v-on:click="close"></div>
    <div class="modal__body">
      <h2 class="modal__title">Создание нового контакта</h2>
      <hr />
      <form class="modal__form" @submit.prevent="onSubmit">
        <input type="text" placeholder="Имя" v-model="name">
        <input type="tel" placeholder="Телефон" v-model="phone">
        <input type="email" placeholder="E-mail" v-model="email">
        <input type="text" placeholder="Организация" v-model="company">
        <div class="modal__buttons">
          <button type="submit" class="modal__btn_back_create btn">Создать</button>
        </div>
      </form>
      <button class="modal__btn_back btn" v-on:click="close">Отмена</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddModalWindow',
  data () {
    return {
      name: '',
      phone: '',
      email: '',
      company: '',
      active: false
    }
  },
  methods: {
    open () {
      this.$emit('open')
    },
    close () {
      this.$emit('close')
    },
    onSubmit () {
      if (this.name.trim() && this.phone.trim()) {
        const newContact = {
          id: Date.now(),
          name: this.name,
          phone: this.phone
        }
        this.$emit('addContact', newContact)
      }
    }
  }
}
</script>

<style lang="scss">
$mainColor: #00BFFF;

input {
  border: none;
  border-bottom: 1px solid #ccc;
  outline: none;
  padding: 5px 0 5px 5px;
  width: 100%;
  margin-bottom: 15px;

  &:focus {
    border-bottom: 1px solid #000;
  }
}

.modal__btn_back_create {
  color: $mainColor;
}
</style>
