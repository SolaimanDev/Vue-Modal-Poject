<template>
<div>
    <h2>{{title}}</h2>

  <div v-if="showModal">
  <!-- <Modal header="Sign up for the giveaway." text="Modal Contenet Here" @close="toggleHandle"></Modal> -->
  <Modal  @close="toggleHandle">
    <template v-slot:links>
      <a href="#"> Read More</a>
      <a href="#"> Sign Up</a>
    </template>
    <h2> Modal Title</h2>
    <p>This is Modal paragraph content</p>
  </Modal>
  </div>
    <button type="button" class="form-control" @click="toggleHandle"> Open Modal</button>
</div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from "./components/Modal.vue";
export default {
  name: 'App',
  components:{Modal},
  data()
  {
    return {
      title:"Hello bangladesh",
      showModal:false,
    }
  },
  methods:{
    // handleClick()
    // {
    //   console.log(this.$refs);
    //   this.$refs.name.classList.add('active');
    //   this.$refs.name.focus();
    // }
    toggleHandle:function (){
this.showModal=!this.showModal ;
    }
  },
 
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
