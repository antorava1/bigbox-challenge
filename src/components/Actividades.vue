<template>
    <div class="card">
        <div class="card-info" v-for="todo in todos" :key="todo.id">
            <div class="card-header">
               <svg xmlns="http://www.w3.org/2000/svg" class="image">
                  <rect width="100%" height="100%" fill="#868e96"></rect>
                  <text x="50%" y="50%" fill="#dee2e6" dy=".3em">Image cap</text>
               </svg>
            </div>
            <div>
                <img class="people-logo" src="../assets/2people.svg">
                <h3 class="title">{{todo.title}}</h3>
            </div>
            <div>
                <img class="location-logo" src="../assets/location.svg">
                <h3 class="location">Ubicación</h3>
            </div>
            <h3 class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae impedit dolorem unde accusamus repellendus iste quo voluptatem inventore animi quam, modi neque quod adipisci atque earum rerum corporis ipsa qui?</h3>
            <h3 class="points">{{todo.points + " puntos"}}</h3>
        </div>
    </div>
</template>

<script>

import axios from 'axios'

export default{
  data () {
    return {
      todos: null
    }
  },
  mounted () {
    this.getTodos()
  },
  methods: {
    getTodos () {
      axios.get('https://json-biglifeapp.herokuapp.com/activity?_limit=9')
        .then(response => {
          console.log(response)
          this.todos = response.data
        })
        .catch(e => console.log(e))
    }
  }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap');
 .card{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    align-self: center;
    flex-direction: row;
    row-gap: 50px;
 }
 .card-info {
    background-color: darkorchid;
    height: 398px;
    width: 369px;
    left: 100px;
    top: 556px;
    border-radius: 5px;
    font-family: Quicksand;
 }
 .image {
   height: 170px;
   width: 369px;
   left: 0px;
   top: 0px;
   border-radius: 4px;
 }
 .title {
    left: 0px;
    top: 254px;
    font-size: 18px;
    font-style: normal;
    text-align: left;
    color: #464646
 }
 .people-logo {
    float: right;
 }
  .location-logo {
    float: left;
 }
 .location {
    height: 18px;
    width: 97px;
    left: 0px;
    top: 289px;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0px;
    text-align: center;
    color: #000000
 }
 .description {
    height: 72px;
    width: 369px;
    left: 0px;
    top: 319px;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0px;
    text-align: left;
    color: #464646
 }
 .points {
    height: 23px;
    left: 0px;
    top: 379px;
    font-size: 18px;
    font-style: normal;
    font-weight: 600;
    line-height: 23px;
    letter-spacing: 0px;
    text-align: left;
    color: #464646
 }
</style>
