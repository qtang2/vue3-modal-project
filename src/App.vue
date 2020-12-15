<template>
  <h1>{{title}}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
    <Modal :header="header" v-bind:text="text" theme="" @close ="toggleModal"  >
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p>
    </Modal>
  </div>
  <button v-on:click.alt="toggleModal">Open Modal(alt)</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return {
      title:"Hello",
      header:"Sign up for the Giveway",
      text:"Grab your ninja swag for half price",
      showModal:false
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
