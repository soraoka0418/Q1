<template>
  <div>
    <div class="modal">
      <button class="button" @click="showModal">
        モーダルの説明
      </button>
      <TemplateModal @close="closeModal" v-if="modal">
        <template class="modal">
          <p>slot: 要素の中に好きなものを入れられる</p>
          <p>emit: 親要素にイベントを伝えられる</p>
          <p>self: イベント要素が自分の時だけ呼び出される</p>
        </template>
      </TemplateModal>
    </div>
  </div>
</template>

<script>
import TemplateModal from "../components/TemplateModal.vue";
export default {
  components: { TemplateModal },
  data() {
    return {
      modal: false
    };
  },
  methods: {
    showModal() {
      this.modal = true;
    },
    closeModal() {
      this.modal = false;
    }
  },
};
</script>

<style>
.button {
  font-size: 18px;
  width: 200px;
  height: 60px;
  background-color: rgb(205, 241, 170);
  outline: none;
  border-radius: 15px;
  border: none;
}
</style>
