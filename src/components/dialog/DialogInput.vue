<template>
  <div class="dialog-input-container">
    <el-input
      type="textarea"
      :rows="6"
      placeholder="请输入内容"
      @change="changeInput"
      v-model="textarea">
    </el-input>
  </div>
</template>

<script>
export default {
  name: 'DialogInput',
  props: {
    time: Number,
    content: String
  },
  data() {
    return {
      textarea: ""
    }
  },
  methods: {
    changeInput() {
      window.EventBus.$emit('inputChange', this.textarea)
    }
  },
  created() {
    window.EventBus.$on('clearInput', () => {
      this.textarea = ""
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
