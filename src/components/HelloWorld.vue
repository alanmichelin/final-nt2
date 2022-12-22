<template>
  <div>
    <h1>Conversor de temperatura</h1>
    <div>
      <div>
        <label for="input_temp">Ingresar temperatura:</label>
        <input type="number" id="input_temp" @input="calcular"/>
      </div>
      <div>
        <label for="temp_f">Conv temperatura °F:</label>
        <input type="number" :style="{color:colorTxt}" id="temp_f" readonly v-model="temperaturas.farenheit">
      </div>
      <div>
        <label for="temp_k">Conv temperatura °K:</label>
        <input type="number" :style="{color:colorTxt}" id="temp_k" readonly v-model="temperaturas.kelvin">
      </div>
    </div>
    <div>
      <h2>Respuestas</h2>
      <ul style="text-align:left">
        <li>a. @click</li>
        <li>b. Crear un proyecto base Vue basado en Vue CLI </li>
        <li>c. Los espacios adelante y atrás en una entrada de texto</li>
        <li>d. Definir el path y el componente activo para esa ruta</li>
        <li>e. La lógica para cambiar el estado global de la aplicación</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return {
      temperaturas:{
        farenheit: '',
        kelvin: ''
      },
      colorTxt:'black'
    }
  },
  methods:{
  calcular(e){
      let valorInput = parseInt(e.target.value)
      this.temperaturas ={
        farenheit: valorInput + 32,
        kelvin: valorInput + 273.15
      }
      this.colorTxt = this.checkColor(valorInput)
    },
  checkColor(num){
    let color = 'black'
    if(!num){
      return color;
    }

    if(num<=0){
      color = 'blue'
    }
    else if(num>0 && num<15){
      color = 'magenta'
    }
    else{
      color= 'red'
    }
    return color;
  }
  }
}
</script>
