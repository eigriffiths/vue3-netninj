<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <div v-if="showModal">
    <!-- Props -->
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal" /> -->
    <!-- Slots -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now!</a>
        <a href="#">More info</a>
      </template>
      <h1>Giveaway!</h1>
      <p>Grab your swag fro half price!</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Open Modal (alt)</button>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links>
        <a href="#">click to proceed!</a>
      </template>
      <h1>Are you sure?</h1>
      <p>Click the following link to proceed</p>
    </Modal>
  </div>
  <button @click="toggleModalTwo">Open Modal two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'Testing Vue App',
      header: 'Sign up for the giveaway!',
      text: 'Grab your ninja swag for half price',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
