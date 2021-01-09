<template>
  <div>
    <div class="modal__background" v-on:click="close"></div>
    <div class="modal__body">
      <h2 class="modal__title">Вы уверены, что хотите удалить выбранный контакт?</h2>
      <hr />
      <div class="modal__buttons">
        <button class="modal__btn_delete btn" v-on:click="$emit('removeContact', contact.id)">Удалить</button>
        <button class="modal__btn_back btn" v-on:click="close">Отмена</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DeleteModal',
  methods: {
    close () {
      this.$emit('close')
    }
  },
  props: ['contact']
}
</script>

<style lang="scss">
$redColor: #B22222;

.modal__background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 99;
  background-color: rgba(0, 0, 0, .3);
}

.modal__body {
  position: fixed;
  top: 50%;
  left: 50%;
  z-index: 100;
  transform: translate(-50%, -50%);
  background-color: #fff;
  width: 100%;
  max-width: 450px;
  padding: 15px;
  border-radius: 8px;
  cursor: default;

  .modal__title {
    font-size: 18px;
    opacity: .6;
  }

  hr {
    margin: 15px 0;
  }

  .modal__buttons {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
  }

  .modal__btn_delete {
    color: $redColor;
  }

  .modal__btn_back {
    opacity: .7;
  }
}

.btn {
  border: none;
  outline: none;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
  padding: 10px;
  background: inherit;
}
</style>
