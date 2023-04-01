<template>
  <header>
    <h1>Incrementador</h1>
    <hr/>
  </header>

  <main>
    <h2>Contador: {{ contador }}px</h2>
    <button @click="increment()"><i class="icon-user-plus"></i></button>
    <button @click="decriment()"><i class="icon-download-cloud"></i></button>
    <button @click="reset()"><i class="icon-heart reset"></i></button>
    <div>
      <img src="./assets/Dragon.svg" alt="dragon" class="dragon">
    </div>
  </main>

</template>

<script>

import './assets/iconos/css/fontello.css'

export default {
  data: () => ({
    contador: 0
  }),
  methods: ({
    increment(){
      this.contador+=10;
      let reset = document.querySelector('.reset');
      let imagen = document.querySelector('.dragon');
      let h2 = document.querySelector('h2');
      if (this.contador < 360) {
        imagen.style.width = `${this.contador}px`
        imagen.style.height = `${this.contador}px`
      
      }if (this.contador > 360) {
        reset.style.color = 'red';
        h2.style.color = 'red';
        alert('La imagen sobrepasa su pantalla, RESET para iniciar de nuevo')
      }else{
        reset.style.color = 'rgba(0, 128, 255, 0.797)';
        h2.style.color = 'rgba(0, 128, 255, 0.797)';
      }
    },

    decriment(){
      this.contador-=10;
      var imagen = document.querySelector('.dragon');
      imagen.style.width = `${this.contador}px`
      imagen.style.height = `${this.contador}px`
    },

    reset(){
      this.contador = 0;
      var imagen = document.querySelector('.dragon');
      imagen.style.height = `${this.contador}px`
      imagen.style.height = `${this.contador}px`
    },
  })
}
</script>

<style scoped>

header {
  width: 50%;
  margin: auto;
  text-align: center;
  font-size: 25px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

main {
  text-align: center;
}

h2 {
  width: 50%;
  font-size: 3rem;
  font-weight: bolder;
  color: rgba(0, 128, 255, 0.797);
  margin: auto;
  border-bottom: 1px solid #8a8888af;
  border-radius: 5px;
}

img {
  width: 100%;
  height: 300px;
  margin-top: -20px;
}

button {
  font-size: 2rem;
  color: rgba(0, 128, 255, 0.797);
  margin: 20px 4px;
  border: 1px solid #c1bfbfaf;
  border-radius: 5px;
}

button:hover {
  color: black;
}

</style>