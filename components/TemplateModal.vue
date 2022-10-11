<template>
  <transition class="modal">
    <div class="modal__overlay" @click.self="$emit('close')">
      <div class="modal__window">
        <div class="modal__content">
          <slot></slot>
        </div>
        <button class="modal-btn" @click="$emit('close')">閉じる</button>
      </div>
    </div>
  </transition>
</template>

<script></script>

<style scoped>
.modal__overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color:rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal__window {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 60%;
  background-color: #fff;
  border-radius: 20px;
  overflow: hidden;
}
.modal__content {
  padding: 20px;
}

.modal-btn {
  width: 200px;
  font-size: 16px;
  outline: none;
  border: none;
  border-radius: 20px;
  padding: 10px 20px;
  margin-top: auto;
  margin-bottom: 20px;
  background-color: rgb(209, 237, 237);
}

.modal-enter{
  opacity: 0;
}

.modal-enter .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>