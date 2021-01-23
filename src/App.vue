<template>
  <div>
   <navbar/>
   <div class="container-fluid">
     
<card/>
  
</div>
</div>

   
   
</template>

<script>
import navbar from './components/nav.vue'
import card from './components/card.vue'



export default {
  name: 'App',
  components: {
    navbar,
    card
  
  }
}
</script>
<style >


.scroller{
overflow-y: scroll;
  max-height: 80.5vh;

}



.vh{
 height: 100%; 
}
.scrollbar::-webkit-scrollbar {
    width: 14px;     /* Tamaño del scroll en vertical */
    height: 10px;    /* Tamaño del scroll en horizontal */
    
}
/* Ponemos un color de fondo y redondeamos las esquinas del thumb */
.scrollbar::-webkit-scrollbar-thumb {
    background: #ffc107;
    border-radius: 10px;
}
/* Cambiamos el fondo y agregamos una sombra cuando esté en hover */
.scrollbar::-webkit-scrollbar-thumb:hover {
    background: #e9b109;
    box-shadow: 0 0 2px 1px rgba(0, 0, 0, 0.2);
}
/* Cambiamos el fondo cuando esté en active */
.scrollbar::-webkit-scrollbar-thumb:active {
    background-color: #ff6a07;
}
/* Ponemos un color de fondo y redondeamos las esquinas del track */
.scrollbar::-webkit-scrollbar-track {
    background: #f1b604;
    border-radius: 10px;
}

/* Cambiamos el fondo cuando esté en active o hover */
.scrollbar::-webkit-scrollbar-track:hover,
.scrollbar::-webkit-scrollbar-track:active {
  background: #ffc10750;
}


</style>
