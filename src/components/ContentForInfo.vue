<template>
  <div class="content">
    <div class="content__body">
      <div class="content__icons">
        <i class="fa fa-pencil-square-o" aria-hidden="true"></i>
        <i class="fa fa-trash" aria-hidden="true"></i>
      </div>
      <div class="content__photo">
        <img src="@/assets/contact-icon.png" alt="" width="150px" height="150px">
      </div>
      <form class="modal__form">
        <input type="text" placeholder="Имя" readonly disabled>
        <input type="tel" placeholder="Телефон" readonly disabled>
        <input type="email" placeholder="E-mail" readonly disabled>
        <input type="text" placeholder="Организация" readonly disabled>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContentInfo'
}
</script>

<style lang="scss">
.content__photo {
  display: flex;
  justify-content: center;
}

.content__icons {
  display: flex;
  justify-content: flex-end;
  font-size: 22px;
  i {
    opacity: .7;
    padding: 0 5px;
  }
}
</style>
