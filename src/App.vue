<script retup>
export default {
  name: 'HelloWorld',
  methods:{
      no(){
      },
      agregar_alumno(){
        var numc = document.getElementById("control").value
        var nomc = document.getElementById("nombre").value
        var ed = document.getElementById("edad").value
        var sem = document.getElementById("semestre").value
        var ca = document.getElementById("carrera").value
        var matagr = document.getElementById("Materias_agregadas").value
        var matesp = document.getElementById("Especialidad").value
        var actext = document.getElementById("Extraescolares").value

        //console.log(nomc);
        if(numc=="" ||  nomc=="" || ed=="" || sem=="" || ca=="" ||  matagr=="" || matesp=="" || actext==""){
          alert("ERROR!, debes asegurarte de hacer puesto informacion en todos los campos")

        }else{
          this.$store.commit("enviarNoControl", numc)
          this.$store.commit("enviarNombre", nomc)
          this.$store.commit("enviarEdad", ed)
          this.$store.commit("enviarSemestre", sem)
          this.$store.commit("enviarCarrera", ca)
          this.$store.commit("enviarMat_agregada", matagr)
          this.$store.commit("enviarMat_especial", matesp)
          this.$store.commit("enviarAct_complementariap", actext)
        }
      }
  }
}
</script>

<template>
  

  <div class="container my-3 pb-3 shadow-lg rounded-4 bg-light">
    <form @submit.prevent="no" >
      <h1 class="fw-bold text-center py-2">Formulario Inscripción Alumnos</h1>
      <div>
        <label class="form-label">Numero de Control</label>
        <input type="text" class="form-control" id="control">

        <label  class="form-label">Nombre</label>
        <input type="text" class="form-control" id="nombre" >

        <label  class="form-label">Edad</label>
        <input type="number" class="form-control" id="edad" >

        <label  class="form-label">Semestre</label>
        <input type="number" class="form-control" id="semestre" >

        <label  class="form-label">Carrera</label><br>
        <div class="btn-group">
          <button type="button" class="btn btn-outline-success">ISC</button>
          <button type="button" class="btn btn-outline-success">IM</button>
          <button type="button" class="btn btn-outline-success">IIA</button>
          <button type="button" class="btn btn-outline-success">CP</button>
          <button type="button" class="btn btn-outline-success">LA</button>
        </div>
        <br><br>
        
        <label  class="form-label">Materias agregadas</label>
        <div>
          <label><input type="checkbox" value="POO"> POO</label>
          <label><input type="checkbox" value="FP"> FP</label>
          <label><input type="checkbox" value="BD"> BD</label>
        </div>
        <br>

        <label  class="form-label">Materias de Especialidad</label>
        <div>
          <select v-model="materiasEspecialidad" multiple>
            <option value="programacion">Programación</option>
            <option value="redes">Redes</option>
            <option value="seguridad">Seguridad</option>
          </select>
        </div>

        <label  class="form-label">Actividades Extraescolares</label>
        <br>
        <textarea v-model="actividadesExtraescolares"></textarea>
      </div>

      <div class="row">
        <div class="col">
          <button  class="btn btn-primary w-100" @click="agregar_alumno">Enviar</button>
        </div>
    </div>
      
    </form>
  </div>

 
</template>

<style scoped>

</style>

<!--
<script setup>

</script>


<template>
  <div class="container my-3 pb-3 shadow-lg rounded-4 bg-light">

    <h2 class="fw-bold text-center py-2">Formulario Registro</h2>

    <form action="#">
       
        <div class="row">
            <label for="" class="col-12 col-sm-2 col-md-3 col-lg-12 col-form-label">Nombre:</label>
            <div class="col-12 col-sm-10 col-md-9 col-lg-12">
                <input type="text" class="form-control">
            </div>
        </div>

        <div class="row">
            <label for="" class="col-12 col-sm-2 col-md-3 col-lg-12 col-form-label">Correo electrónico</label>
            <div class="col-12 col-sm-10 col-md-9 col-lg-12">
                <input type="email" name="email" class="form-control">
            </div>
        </div>

        <div class="row">
            <label for="" class="col-12 col-sm-2 col-md-3 col-lg-12 col-form-label">Dirección</label>
            <div class="col-12 col-sm-10 col-md-9 col-lg-12">
                <input type="text" class="form-control">
            </div>
        </div>

        <div class="row">
            <label for="" class="col-12 col-sm-2 col-md-3 col-lg-12 col-form-label">Teléfono</label>
            <div class="col-12 col-sm-10 col-md-9 col-lg-12">
                <input type="tel" class="form-control">
            </div>
        </div>

        <div class="row my-3">
            <label class="col-12">
                <select name="" class="form-select" id="">
                    <option selected>Carrera</option>
                    <option value="">ISC</option>
                    <option value="">IM</option>
                    <option value="">IIA</option>
                    <option value="">LA</option>
                </select>
            </label>
        </div>

        <div class="row">
            <div class="col">
                <button class="btn btn-outline-success w-100">Enviar</button>
            </div>
            <div class="col">
                <button class="btn btn-outline-danger w-100">Cancelar</button>
            </div>
        </div>

    </form>
</div>
</template>

<style scoped>
</style>
-->
<!--
<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
-->