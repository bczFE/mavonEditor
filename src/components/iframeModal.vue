<template>
  <div v-if="showModal" class="iframeModal">
    <img src="../lib/close.png" class="close" @click="closeModal">
    <div class="container">
      <span>url:</span>
      <input type="text" v-model="iframeData.src">
    </div>
    <div class="container">
      <span>宽度:</span>
      <input type="text"  v-model="iframeData.width">
    </div>
    <div class="container">
      <span>高度:</span>
      <input type="text"  v-model="iframeData.height">
    </div>
    <div class="button" @click="commit">确定</div>
  </div>
</template>
<script>
export default {
  name: "iframeModal",
  data () {
    return {
      showModal: false,
      iframeData: {
        src: '',
        width: '',
        height: ''
      }
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
      position: absolute;
      width: 50%;
      height: 50%;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #f5f5f5;
      padding: 20px;
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
  .container{
    width: 80%;
    margin: 20px auto;
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



