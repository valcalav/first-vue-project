<template>
    <h1>{{title}}</h1>
    <p>Welcome</p>
    <!-- <input type="text" ref="name">
    <button @click="handleClick">click me</button> -->
    <div v-if="showModal">
      <Modal theme='sale' @close='toggleModal'>
        <template v-slot:links>
          <a href="#">Sign up now</a>
          <a href="#">More info here</a>
        </template>
        <h1>This is the header</h1>
        <p>This is the text</p>
      </Modal>
    </div>
    <button @click="toggleModal">Open modal</button>
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
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
//  handleClick() {
//    console.log(this.$refs.name)
//    this.$refs.name.classList.add('active')
//  }
  }
}
</script>

<style>
#app {
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
