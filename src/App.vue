<template>
  <h1> {{title}} </h1>
  <p> Welcome </p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info.</a>
      </template>

      <h1> Giveaway!</h1>

    </Modal>
  
  </div>

  <div v-if="showModal2">
    <Modal2 theme="sale" @close="toggleModal2">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info.</a>
      </template>

      <h1> Enter The Competition!</h1>

    </Modal2>
  
  </div>
  <button @click="toggleModal">open modal1</button>
  <button @click="toggleModal2">open modal2</button>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
</template>

<script>
import Modal from './components/Modal.vue'
import Modal2 from './components/Modal2.vue'

export default {
  name: 'App',
  components:{Modal,Modal2},
  data() {
    return{
      title: 'My First Vue App :)',
      text: "Grab for 1/2 price!",
      showModal: false,
      showModal2:false
    }
    
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name)
    },
    toggleModal(){
      this.showModal = !this.showModal

    },
    toggleModal2(){
      this.showModal2 = !this.showModal2

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
