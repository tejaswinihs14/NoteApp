<template>
 <div id="app">
  <Navbar @openModal="modal=true"/> 
  <div class="modal" v-if="modal">
    <div class="title-wrap">
        <div class="title">Enter title</div>
        <div class="close-btn" @click.self="handleNoteAddLocal(note_title, note_data)"> 👍 </div>
      </div>
  </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';

export default {
  name: "App",
  components: {
    Navbar
  },

  data(){
    return{
        modal:false,
        note_title: "",
        note_data: "",
    }
  },
    methods:{
    handleNoteAddLocal(note_title, note_data) {
      this.note_title = "";
      this.note_data = "";
      this.handleNoteAdd(note_title, note_data);
    },
  }
};
</script>

<style lang="scss" scoped>

body{
  margin: 0px;
  padding: 0px;
}

.modal{
  width: 40%;
  height: 50vh;
  background-color: #161616;;
  position: absolute;
  top: 30%;
  left: 30%;

  .title-wrap{
    background-color: #0ff;
    height: 5vh;
    display: flex;
    padding: 10px 10px;
    justify-content: center;
    align-items: center;

    .title{
      font-size: 24px;
      font-weight: 700;
    
      padding: 8px 10px;
    }

    .close-btn{
      padding: 8px 10px 8px 10px;
      font-size: 24px;
      font-weight: 700;
      
    }
  }
}
</style>
