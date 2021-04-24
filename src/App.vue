<template>
<div id="app">
  <Navbar @openModal="modal=true"/> 
  <div class="modal" v-if="modal">
    <form @submit.prevent="submitNote">
    <div class="title-wrap">
      <input class="title" placeholder="Enter title" v-model="note.title" required />
      <button class="close-btn" type="submit" > 👍 </button>
      <div class="close-btn" @click="closebtn">⛔</div>
    </div>
    <textarea placeholder="Enter your note details" v-model="note.detail" required/>
    </form>
  </div>
  <div class="card-wrap"  v-if="savedNotes.length > 0" >
    <div class="cards" v-for='savedNote in savedNotes' :key="savedNote" >
      <p class="title">{{savedNote.title}}</p>
      <p class="detail">{{savedNote.detail}}</p>
    </div>
  </div>
  <div class="empty-state" v-else>
    <p>No notes available.<br> Please create new note</p>
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
        savedNotes:[],
        note:{
          title:'',
          detail:''
        }
    }
  },
    methods:{
    closebtn(){
        this.modal = false; 
      },

    submitNote(){
      let tempNote = {...this.note};
      this.savedNotes.push(tempNote);
      this.note.title='';
      this.note.detail='';
      this.modal = false; 
    }
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
  background-color: #161616;
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
      background-color: #0ff;
      border: none;
      outline: none;
    }

    .close-btn{
      padding: 8px 10px 8px 10px;
      font-size: 24px;
      font-weight: 700;
      cursor: pointer;
      background-color: #0ff;
      border: none;
      outline: none;
    }
  }

  textarea{
    color: #fff;
    background-color: #161616;
    border: none;
    width: 100%;
    height: 100%;
    padding: 5px 5px;
    
    &::-webkit-scrollbar{
      display: none;
    }
  }
}

.card-wrap{
  padding: 100px 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  
  .cards{
  width: 200px;
  height: 200px;
  background-color: #8EE4AF;;
  cursor: pointer;
  padding:16px;
  margin-bottom: 20px;

    &:hover{
      transform: scale(1.1);
      box-shadow: 1px 1px 10px  #8EE4AF;
    }

  .title{
    font-size: 16px;
    font-weight: 700;
    margin: 0 0 20px 0;
  }

  .detail{
    font-size: 12px;
    font-weight: 500;
    margin: unset;
  }
}
}
.empty-state{
  height: 50vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #161616;
  font-size: 24px;
  font-weight: 700;
}

</style>
