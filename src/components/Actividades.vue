<template>
  <div class="container">
    <div class="card">
        <div class="card-info" v-for="todo in todos" :key="todo.id">
            <div class="card-header">
               <img src="../assets/card4.jpg" class="image">
            </div>
            <div>
                <img class="people-logo" src="../assets/2people.svg">
                <h3 class="title">{{todo.title}}</h3>
            </div>
            <div>
                <img class="location-logo" src="../assets/location.svg">
                <h3 class="location">Ubicación</h3>
            </div>
            <h3 class="description">{{todo.activity.description}}</h3>
            <h3 class="points">{{todo.points + " puntos"}}</h3>
        </div>
    </div>
    <div class="text-center">
  </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      todos: null,
      page: 1
    }
  },
  mounted () {
    this.getTodos()
  },
  methods: {
    getTodos () {
      fetch('https://json-biglifeapp.herokuapp.com/activity/?_limit=9')
        .then(res => res.json())
        .then(data => {
          console.log('Antes de parsear', data)
          this.todos = data.map(el => {
            return {
              ...el,
              activity: JSON.parse(el.activity)
            }
          })
          console.log('Parseado activity', this.todos)
        })
    }
  }
}

var parse = require('parse-link-header')
var linkHeader =
  '<http://json-biglifeapp.herokuapp.com/activity?_page=2>; rel="next", ' +
  '<http://json-biglifeapp.herokuapp.com/activity?_page=1>; rel="first", ' +
  '<http://json-biglifeapp.herokuapp.com/activity?_page=213>; rel="last"'

var parsed = parse(linkHeader)
console.log(parsed)
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
    height: 398px;
    width: 369px;
    left: 100px;
    top: 556px;
    border-radius: 5px;
    font-family: Quicksand;
 }
 .image {
   height: 200px;
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
