<template>
  <h1>{{ title }}</h1>
  <p>Whale cum</p>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">click me</button> -->
  <teleport to="#modals" v-if="showModal1">
    <Modal theme="sale" @close="toggleModal1">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="https://evrysome.com/" target="_blank">more info</a>
      </template>
      <h1>Hey, my name Thomas Tomska Ridgewell</h1>
      <p>and welcome back to #CONTENT</p>
    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModal2"> <!--Dette er mitt forslag til utfordringen. Det var riktig! Woohoo. -->
    <Modal theme="buy" @close="toggleModal2">
      <template v-slot:links2>
        <a href="#">stupid girl</a>
        <a href="https://evrysome.com/" target="_blank">more info</a>
      </template>
      <h1>Hey, my name is not Thomas Tomska Ridgewell</h1>
      <p>and welcome back to #last week</p>
    </Modal>
  </teleport>
  <button @click="toggleModal1">open modal 1</button>
  <button @click="toggleModal2">Ambitions</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'My First Vue App 8===D',
      // header: 'See you last week.',
      // text: 'Oh, fuck off',
      showModal1: false,
      showModal2: false,
    }
  },
  methods: {
    toggleModal1(){
      this.showModal1 = !this.showModal1
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2
    },
  }
}
</script>


<style>
*{
  user-select: none;
}
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
