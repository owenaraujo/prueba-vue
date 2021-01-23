<template>
  <div>

      <div class="d-none" v-for="comp of componentes" >

          <h5 v-bind:class="{'bg-warning' : comp.status }" >{{comp.nombre}}</h5>
      </div>
<div class="row row-cols-4 scroller scrollbar">
    <div v-for="list of info">
      <div class="col mb-3 mt-4">
        <div class="desabilitado" v-bind:class="{'d-none': list.active}"  ></div>
        <div class="card" style="width: 18rem">
          <img
            v-bind:src="list.poster"
            class="card-img-top"
            alt="..."
            style="height: 200px"
          />

          <div class="card-body">
            <h5>{{ list.nombre }}</h5>
            <h5>{{ list.categoria }}</h5>
<div class="d-flex align-items-center">
            <button class="btn btn-sm w-50 bg-success text-white">acceder</button><p class=" ml-5 text-right">${{ list.precio }}</p>
    
    </div>            
          </div>
        </div>
      </div>
    </div>
  </div>

      <div class=" d-flex justify-content-center">
<nav aria-label="...">
  <ul class="pagination">
    <div class="page-item " @click="chargePage(page - 1)">
      <a class="page-link" href="#" tabindex="-1">anterior</a>
    </div>
    <li class="page-item"><a class="page-link" href="#">{{page}}</a></li>
    
    
    <div class="page-item"  @click="chargePage(page + 1)">
      <a class="page-link" href="#"  >siguiente</a>
    </div>
  </ul>
</nav>



      </div>

  </div>
</template>
<script>
export default {
  name: "card",
  data() {
    return {
      info: null,
      page: 1,
      pages: 1,
      componentes :[
{nombre : "owen" , status: true},
{nombre : "owen" , status: true},
{nombre : "owen" , status: false},
{nombre : "owen" , status: true},
{nombre : "owen" , status: false},
{nombre : "owen" , status: true},
{nombre : "owen" , status: false},


      ]
    };
  },
  created(){
this.fetch()
  },
  methods: {
      fetch (){
const param =this.page
      
       axios
      .get(`http://agile-dusk-92931.herokuapp.com/api/cursos?page=${param}`, )
      .then((response) => (
          this.info = response.data.cursos.data,
          this.pages = response.data.cursos.last_page
          
      ));




      },
      chargePage(page){
          this.page = page <= 0 || page > this.pages ? this.page : page;
          this.fetch()


      }
  },
};
</script>
<style >
.desabilitado {
  height: 100%;
  width: 18rem;
  background: black;
  position: absolute;
  z-index: 1000;
  opacity: 50%;
}
</style>