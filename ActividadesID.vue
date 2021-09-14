<template>
    <main class="main">
        <header v-for="todo in todos" :key="todo.id">
            <div>
              <img src="../assets/card4.jpg" class="image">
            <div class="header-text">
                <h3 class="title">{{todo.title}}</h3>
                <h3 class="description">{{todo.activity.description}}</h3>
                <div>
                    <img class="people-logo" src="../assets/2people.svg">
                    <h3 class="people">Para {{todo.participants === 1 ? todo.participants + ' persona' : todo.participants + ' personas'}}</h3>
                </div>
                <div>
                    <img class="location-logo" src="../assets/locationblack.svg">
                    <h3 class="location">Ubicación</h3>
                </div>
                <h3 class="points">{{todo.points}} puntos</h3>
            </div>
        </header>
        <aside class="includes">
            <h3 class="subtitle">¿Qué incluye?</h3>
            <img class="underlined" src="../assets/underlined.svg">
            <p><strong>BOX PICOTEO</strong></p>
            <ul>
                <li>500gr Quiche.</li>
                <li>600gr Aros de cebolla.</li>
                <li>500gr Bondiola braseada.</li>
                <li>8 Empanadas de lomo.</li>
                <li>6 Croquetas de cordero.</li>
                <li>8 Buñuelos de espinaca.</li>
                <li>8 Canastitas de gruyere y champignon.</li>
                <li>700gr Papas fritas con cheddar y cebolla de verdeo.</li>
                <li>Alioli-Barbacoa-Honey Mustard.</li>
                <li>4 Postre Oreo.</li>
            </ul>
            <p><em>Recibirán una box con los platos envasados al vacio. Estarán listos para regenerar y terminarlos con las instrucciones correspondientes.</em></p>
        </aside>
        <aside class="includes">
            <div>
                <img class="rules-logo" src="../assets/ruleslogo.svg">
                <h3 class="subtitle2">Reglas: </h3>
                <h4 class="rules-description">Envío incluído de lunes a sábados en las siguientes zonas: Beccar, San Isidro, Martínez, Acassuso, La Lucila, Olivos, Vicente López. Para reservar comunicarse con 48hs de anticipación por mail a info@cateringlaestaca.com o los siguientes números: 11 3908 0802 o 4766 6625 interno 133.</h4>
            </div>
        </aside>
    </main>
</template>

<script>
export default {
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
      fetch('https://json-biglifeapp.herokuapp.com/activity?_limit=1')
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
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap');
.main {
    font-family: Quicksand;
}
.header-text{
    margin-left: 580px;
    margin-top: -380px;
}
.image {
    height: 371px;
    top: 111px;
    border-radius: 8px;
    object-fit: cover;
}
.includes {
    margin-top: 180px;
    margin-right: 750px;
}
.title {
    height: 38px;
    width: 196px;
    left: 696px;
    top: 111px;
    font-size: 30px;
    font-style: normal;
    font-weight: 700;
    line-height: 38px;
    letter-spacing: -1px;
    text-align: left;
    color: #464646;
 }
 .people {
    height: 20px;
    margin-left: 30px;
    top: 0px;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    text-align: left;
    color:#464646
 }
 .people-logo {
    float: left;
 }
  .location-logo {
    float: left;
    color: #464646
 }
 .location {
    height: 20px;
    margin-left: 30px;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    color: #464646
 }
 .description {
    height: 70px;
    width: 600px;
    left: 696px;
    top: 169px;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 23px;
    letter-spacing: 0px;
    text-align: left;
    color: #4F4F4F;

 }
 .points {
    height: 30px;
    width: 137px;
    left: 698px;
    top: 384px;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px;
    letter-spacing: 0px;
    text-align: left;
    color: #464646
 }
 .subtitle {
    height: 57px;
    width: 151px;
    left: 113px;
    top: 579px;
    font-size: 22px;
    font-style: normal;
    font-weight: 500;
    line-height: 28px;
    letter-spacing: -1px;
    text-align: left;
    color:#464646
 }
 .underlined {
    height: 2.99310302734375px;
    width: 156.11550903320312px;
    left: 100.07421875px;
    border-radius: 0px;

 }
 .list-text {
    height: 158px;
    width: 565px;
    left: 100px;
    top: 671px;
    font-size: 18px;
    font-style: normal;
    font-weight: 300;
    line-height: 23px;
    letter-spacing: 0px;
    text-align: left;
    color:#4F4F4F
 }
 .includes-text{
    height: 82px;
    width: 564px;
    left: 101px;
    top: 806px;
    font-size: 18px;
    font-style: normal;
    font-weight: 300;
    line-height: 23px;
    letter-spacing: 0px;
    text-align: left;
    color: #4F4F4F
 }
 .rules-logo {
    float: left;
 }
 .subtitle2 {
    height: 28px;
    margin-left: 30px;
    margin-top: -100px;
    font-size: 22px;
    font-style: normal;
    font-weight: 700;
    line-height: 28px;
    letter-spacing: -1px;
    text-align: left;
    color:#464646
 }
 .subtitle3{
    height: 30px;
    width: 292px;
    left: 100px;
    top: 1111px;
    font-size: 24px;
    font-style: normal;
    font-weight: 700;
    line-height: 30px;
    letter-spacing: -1px;
    text-align: left;
    color:#464646
 }
 .rules-description {
    height: 52px;
    width: 553px;
    left: 102px;
    top: 995px;
    font-size: 18px;
    font-style: normal;
    font-weight: 300;
    line-height: 23px;
    letter-spacing: 0px;
    text-align: left;
    color: #4f4f4f
 }
</style>
