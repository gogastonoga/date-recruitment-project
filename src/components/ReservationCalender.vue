<script>

export default {
  name: 'modal',
  methods: {
    handleFocusOut () {
      this.$emit('close')
    },
    handleFocus () {
    }
  }
}
</script>
<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal"
           role="dialog"
           aria-labelledby="modalTitle"
           aria-describedby="modalDescription"
           @focus="handleFocus"
           @focusout="handleFocusOut"
           tabindex="0">
        <header
          class="modal-header"
          id="modalTitle">
          <slot name="header">
            March 2017
          </slot>
        </header>
        <section
          class="modal-body"
          id="modalDescription">
          <slot name="body">
            Calendar body
          </slot>
        </section>
      </div>
    </div>
  </transition>
</template>

<style>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal {
  background: #FFFFFF;
  box-shadow: 2px 2px 20px 1px;
  overflow-x: auto;
  display: flex;
  flex-direction: column;
}
.modal-header {
  padding: 15px;
  display: flex;
}
.modal-header {
  border-bottom: 1px solid #eeeeee;
  color: #4AAE9B;
  justify-content: space-between;
}
.modal-body {
  position: relative;
  padding: 20px 10px;
}
</style>
