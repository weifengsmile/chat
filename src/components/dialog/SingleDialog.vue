<template>
  <div class="single-container">
    <div class="time" v-if="showTime">{{ timeDisplay }}</div>
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
    content: String,
    showTime: Boolean
  },
  data() {
    return {
      positionIsLeft: this.position == "left",
      timeDisplay: this.timestamp2Time(this.time)
    }
  },
  methods: {
    timestamp2Time(timestamp) {
      let date = new Date(timestamp)
      let Y = date.getFullYear() + '-'
      let monthNum = date.getMonth() + 1
      let M = (monthNum < 10 ? ('0' + monthNum) : monthNum) + '-'
      let dayNum = date.getDate()
      let D = (dayNum < 10 ? ('0' + dayNum) : dayNum) + ' '
      let hourNum = date.getHours()
      let h = (hourNum < 10 ? ('0' + hourNum) : hourNum) + ':'
      let minNum = date.getMinutes()
      let m = (minNum < 10 ? ('0' + minNum) : minNum)
      return `${Y}${M}${D}${h}${m}`
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
.time {
  height: 20px;
}
</style>
