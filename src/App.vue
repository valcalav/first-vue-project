<template>
    <h1>{{title}}</h1>
    <p>Welcome</p>
    <!-- <input type="text" ref="name">
    <button @click="handleClick">click me</button> -->
    <teleport to=".modals" v-if="showModal">
      <Modal theme='sale' @close='toggleModal'>
        <template v-slot:links>
          <a href="#">Sign up now</a>
          <a href="#">More info here</a>
        </template>
        <h1>This is the header</h1>
        <p>This is the text</p>
      </Modal>
    </teleport>

    <teleport to=".modals" v-if='showModalTwo'>
      <Modal @close='toggleModalTwo'>
        <h1>This is the header of modal2</h1>
        <p>This is the text of modal2</p>
      </Modal>
    </teleport>

    <button @click="toggleModal">Open modal</button>
    <button @click="toggleModalTwo">Open modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first Vue App :) !',
      header: 'This is the header prop',
      text: 'This is the text prop',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
//  handleClick() {
//    console.log(this.$refs.name)
//    this.$refs.name.classList.add('active')
//  }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
