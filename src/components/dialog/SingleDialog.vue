<template>
  <div class="single-container">
    <div :class="['dialog-left', 'dialog']" v-if="positionIsLeft">
        <img class="avatar" src="../../assets/avatar.png" alt="">
        <div class="name-content">
          <p class="name">{{ name }}</p>
          <div class="content content-left">{{ content }}</div>
        </div>
    </div>
    <div :class="['dialog-right', 'dialog']" v-if="!positionIsLeft">
      <div class="content content-right">{{ content }}</div>
      <img class="avatar" src="../../assets/avatar.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'SingleDialog',
  props: {
    position: String,
    time: Number,
    name: String,
    content: String
  },
  data() {
    return {
      positionIsLeft: this.position == "left"
    }
  },
  created() {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dialog {
  margin: 20px 50px;
  display: flex;
  flex-direction: row;
}
.dialog-left {
  justify-content: flex-start;
}
.dialog-right {
  justify-content: flex-end;
}
.name-content {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 20px;
  margin-top: -20px;
}
.content {
  display: flex;
  flex-direction: row;
  background-color: white;
  padding: 10px;
  border-radius: 10px;
  text-align: left;
}

.content-left {
  max-width: 60%;
  background-color: white;
}

.content-right {
  max-width: 60%;
  margin-right: 20px;
  background-color: yellow;
}

.avatar {
  width: 30px;
  height: 30px;
  display: block;
}
</style>
