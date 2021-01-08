<template>
  <div>
    <div class="delete__background" v-on:click="close"></div>
    <div class="delete__modal">
      <p class="delete__modal-text">Вы уверены, что хотите удалить выбранный контакт?</p>
      <hr />
      <div class="delete__modal-buttons">
        <button class="delete__modal-btn_yes btn" v-on:click="$emit('removeContact', contact.id)">Удалить</button>
        <button class="delete__modal-btn_no btn" v-on:click="close">Отмена</button>
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
  props: {
    contact: {
      type: Object
    }
  }
}
</script>

<style lang="scss">
$redColor: #B22222;

.delete__background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 99;
  background-color: rgba(0, 0, 0, .3);
}

.delete__modal {
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

  .delete__modal-text {
    font-size: 16px;
    opacity: .6;
  }

  hr {
    margin: 15px 0;
  }

  .delete__modal-buttons {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
  }

  .delete__modal-btn_yes {
    color: $redColor;
  }

  .delete__modal-btn_no {
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
