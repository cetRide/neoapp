<template>
  <div class="container">
    <h1 class="text-primary">Neo Lights Application</h1>
    <div class="row mt-5" style="height: 500px">
      <div class="col-md-4 card">
        <div class="row p-2">
          <button class="btn btn-success px-5" @click="selectForm">Text
          </button>
          <button class="btn btn-primary px-5 ml-3" @click="selectFont">Fonts
          </button>
          <div v-if="form">
            <h3 class="mt-4">Enter the text</h3>
            <form class="mt-5">
              <textarea class="form-control" v-model="text" cols="40" rows="5"></textarea>
            </form>
          </div>
          <div v-if="font">
            <h3 class="mt-4">Select the font</h3>
            <button class="btn" @click="selectDancing">
              Dancing Script</button>
              <button class="btn" @click="selectChila">
                Chilanka
              </button>
        </div>
      </div>
    </div>
    <div class="col-md-7 bg ml-4 card">
      <div class="row p-2">
        <button class="btn btn-success mr-2" @click="setGlow">ON</button>
        <button class="btn btn-danger" @click="setUnglow">OFF</button>
      </div>
      <div v-if="glow">
        <h3 v-if="dancing" class="mt-5 py-5 text-white glow font-a" style="font-size: 50px">{{text}}</h3>
        <h3 v-if="chila" class="mt-5 py-5 text-white glow font-b" style="font-size: 50px">{{text}}</h3>
      </div>
      <div v-if="unglow">
        <h3 v-if="dancing" class="mt-5 py-5 text-white font-a" style="font-size: 50px">{{text}}</h3>
        <h3 v-if="chila" class="mt-5 py-5 text-white font-b" style="font-size: 50px">{{text}}</h3>
      </div>

    </div>
  </div>
    <div>
      <h6 class="mt-5">By @cetricokola</h6>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        text: 'My text',
        form: true,
        font: false,
        glow: true,
        unglow: false,
        dancing: true,
        chila: false
      }
    },
    methods: {
      selectFont () {
        this.form = false
        this.font = true
      },
      selectForm () {
        this.form = true
        this.font = false
      },
      setGlow () {
        this.glow = true
        this.unglow = false
      },
      setUnglow () {
        this.glow = false
        this.unglow = true
      },
      selectChila () {
        this.dancing = false
        this.chila = true
      },
      selectDancing () {
        this.dancing = true
        this.chila = false
      }
    }
  }
</script>

<style scoped>
  .bg {
    background-color: #464e55;
  }

  .glow {
    font-size: 80px;
    color: #fff;
    text-align: center;
    -webkit-animation: glow 1s ease-in-out infinite alternate;
    -moz-animation: glow 1s ease-in-out infinite alternate;
    animation: glow 1s ease-in-out infinite alternate;
  }

  @-webkit-keyframes glow {
    from {
      text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #e60073, 0 0 40px #e60073, 0 0 50px #e60073, 0 0 60px #e60073, 0 0 70px #e60073;
    }

    to {
      text-shadow: 0 0 20px #fff, 0 0 30px #ff4da6, 0 0 40px #ff4da6, 0 0 50px #ff4da6, 0 0 60px #ff4da6, 0 0 70px #ff4da6, 0 0 80px #ff4da6;
    }
  }

  .font-a {
    font-family: 'Dancing Script', cursive;
  }

  .font-b {
    font-family: 'Chilanka', cursive;
  }

</style>
