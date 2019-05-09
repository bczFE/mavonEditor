<template>
  <div v-if="showModal" class="iframeModal">
    <img src="https://ali.baicizhan.com/readin/images/book_wiki/img_1554134595_818459816" class="close" @click="closeModal">
    <textarea class="iframeContainer" v-model="iframeData"></textarea>
    <div class="button" @click="commit">确定</div>
  </div>
</template>
<script>
export default {
  name: "iframeModal",
  data () {
    return {
      showModal: false,
      iframeData: ''
    }
  },
  methods: {
    startModal () {
      this.showModal = true
    },
    closeModal () {
      this.showModal = false
    },
    commit () {
      this.$emit('iframeAdd', this.iframeData);
      this.closeModal()
    }
  }
}
</script>
<style scoped>
  .iframeModal {
      position: fixed;
      width: 350px;
      height: 200px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #f5f5f5;
      padding: 50px;
      z-index: 100;
  }
  .close {
    position: absolute;
    top: 10px;
    right: 10px;
    width: 30px;
    height: 30px;
    background-color: transparent;
    cursor: pointer;
  }
  .iframeContainer{
    width: 100%;
    height: 100px;
    padding: 5px;
  }
  .button{
    width: 60px;
    height: 30px;
    border-radius: 5px;
    background: #fff;
    margin: 30px auto;
    line-height: 30px;
    text-align: center;
    cursor: pointer;
  }
  .button:hover{
    background-color: #999;
  }
</style>



