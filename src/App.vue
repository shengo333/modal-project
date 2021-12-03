<template>
<h1>{{title}}</h1>
<teleport to=".modals" v-if="showModal">
  <Modal theme="sale" @close="toggleModal">
    <template v-slot:links> 
      <a href="#">sign up now</a>
      <a href="#">more info</a>
    </template>
    <h1>Ninja Givaway</h1>
    <p>Grab your ninja swag for half price!</p>
  </Modal>
</teleport>
  <teleport to=".modals" v-if="showModaltwo">
  <Modal theme="" @close="toggleModaltwo">
    <template v-slot:links> 
      <a href="#">sign up now</a>
      <a href="#">more info</a>
    </template>
    <h1>Beka modal Givaway</h1>
    <p>Grab your modal for free!</p>
  </Modal>
</teleport>


<p>welcome</p>
<button @click.alt="toggleModal">open modal (alt) </button>
<button @click.alt="toggleModaltwo">open modaltwo (alt) </button>

</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  
  data(){
    return{
    title: 'my first but not exactly Vue App',
    showModal: false,
    showModaltwo: false,
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModaltwo(){
      this.showModaltwo = !this.showModaltwo
    },
    handleclick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}

</style>
