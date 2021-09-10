<template>
    <main class="main">
        <header>
            <svg xmlns="http://www.w3.org/2000/svg" class="image">
                <rect width="100%" height="100%" fill="#868e96"></rect>
                <text x="50%" y="50%" fill="#dee2e6" dy=".3em">Image cap</text>
            </svg>
            <div class="header-text">
                <h3 class="title">¡1 player Start!</h3>
                <h3 class="description">Una hora de juego ilimitado en tus fichines favoritos en Bar el Destello, con una cerveza y sándwich a elección.</h3>
                <div>
                    <img class="people-logo" src="../assets/2people.svg">
                    <h3 class="people">Para 2 personas</h3>
                </div>
                <div>
                    <img class="location-logo" src="../assets/locationblack.svg">
                    <h3 class="location">Ubicación</h3>
                </div>
                <h3 class="points">2500 puntos</h3>
            </div>
        </header>
        <aside class="includes">
            <h3 class="subtitle">¿Qué incluye?</h3>
            <img class="underlined" src="../assets/underlined.svg">
            <ul class="list-text">
                <li>Un pase libre de 1 hora en Bar el Destello, para jugar a tus fichines retro favoritos.</li>
                <li>Una cerveza, sidra o vermut y sandwich a elección.</li>
            </ul>
            <h3 class="includes-text">Hay 14 arcades y un flipper en sus muebles originales. Para saber si todavía sos tan bueno como crees en el Tetris, o para terminar de una vez por todas el Wonderboy. </h3>
        </aside>
        <aside class="includes">
            <div>
                <img class="rules-logo" src="../assets/ruleslogo.svg">
                <h3 class="subtitle2">Reglas: </h3>
                <h3 class="rules-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi est nunc pretium vitae vulputate purus.</h3>
            </div>
        </aside>
        <section class="other-activities">
            <h3 class="subtitle3">Otras actividades similares</h3>
        </section>
    </main>
</template>

<script>
export default {

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
    width: 563px;
    left: 100px;
    top: 111px;
    border-radius: 4px;

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
    height: 46px;
    width: 466px;
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
 .rules-text {
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
</style>
