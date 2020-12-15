<template>
  <h1>{{title}}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
    <Modal  theme="" @close ="toggleModal"  >
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
      <h1>Sign up </h1>
      <p>Grab the code to get half price</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal  @close="toggleModalTwo">
      <h1>Successfully logged in</h1>
      <p>Now you can explore the website</p>
    </Modal>
  </div>
  <button v-on:click.alt="toggleModal">Open Modal(alt)</button>
  <button v-on:click="toggleModalTwo">Open ModalTwo</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: {
    Modal,
  },
  data(){
    return {
      showModal:false,
      showModalTwo:false
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.boo)
      this.$refs.boo.classList.add('activr')
      this.$refs.boo.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
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
</style>
