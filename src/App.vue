<template>
  <div id="app">
    <div class="container" :style="{ height: (screenHeight - 150) + 'px' }">
      <p>欢迎进入ele聊天系统</p>
      <div class="dialogs">
        <single-dialog name="ajinga" content="hello, world" position="left"/>
        <single-dialog name="ajinga" content="hello, worldhello, worldhello, worldhello, worldhello, world" position="right"/>
        <single-dialog name="ajinga" content="hello, world" position="left"/>
        <single-dialog name="ajinga" content="hello, world" position="right"/>
        <single-dialog name="ajinga" content="hello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, world" position="left"/>
        <single-dialog name="ajinga" content="hello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, worldhello, world" position="right"/>
        <single-dialog name="ajinga" content="hello, world" position="left"/>
        <single-dialog name="ajinga" content="hello, world" position="right"/>
        <single-dialog name="ajinga" content="hello, world" position="left"/>
        <single-dialog name="ajinga" content="hello, world" position="right"/>
        <single-dialog name="ajinga" content="hello, world" position="left"/>
      </div>
      <div class="dialog-input"><dialog-input /></div>
      <div class="buttons"><el-button type="info" size="medium" round class="send-button">发送</el-button></div>
    </div>
  </div>
</template>

<script>
import SingleDialog from './components/dialog/SingleDialog.vue'
import DialogInput from './components/dialog/DialogInput.vue'

export default {
  name: 'app',
  components: {
    SingleDialog,
    DialogInput
  },
  data() {
    return {
      screenHeight: window.screen.height,
      dialogInputHeight: 400,
      time: 1566661442
    }
  },
  methods: {

  },
  created() {
    console.log(this.screenHeight)
  }
}
</script>

<style>
body {
  background-color:lightgray;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0 auto;
  text-align: center;
  color: #2c3e50;
}
.container {
  display: flex;
  flex-direction: column;
}
.dialogs {
  display: flex;
  flex-direction: column;
  overflow-y:auto;
  padding: 20px 0;
  /* border: #2c3e50 1px solid; */
}
.dialog-input {
  margin-top: 20px;
  padding: 0 50px;
}
.buttons {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  padding-right: 50px;
  margin-top: 10px;
}
</style>
