<template>
  <div>
    <label for="country">País:</label>
    <select id="country" v-model="selectedCountry" @change="updateProvinces">
      <option v-for="country in countries" :value="country.nombre">{{ country.nombre }}</option>
    </select>
    <br>
    <label for="province">Provincia:</label>
    <select id="province" v-model="selectedProvince" @change="updateCities">
      <option v-for="province in provinces[0].nombre" :value="province">{{ province }}</option>
    </select>
    <br>
    <label for="city">Ciudad:</label>
    <select id="city" v-model="selectedCity">
      <option v-for="city in cities" :value="city">{{ city }}</option>
    </select>
  </div>
</template>
  
<script>
//import json from '../assets/paises.json'
export default {
  // Aquí iría la lógica para cargar los datos de los países y provincias
  // y para filtrar las provincias y ciudades según lo seleccionado en los selects
  data() {
    return {
      countries: [], // lista de países
      provinces: [], // lista de provincias
      cities: [], // lista de ciudades
      selectedCountry: '', // país seleccionado
      selectedProvince: '', // provincia seleccionada
      selectedCity: '', // ciudad seleccionada
    }
  },
  mounted() {
    const paises = [
      {
        "nombre": "Argentina",

      },
      {
        "nombre": "México",

      }
    ];
    const provincias = [
      {
        "nombre": ["Buenos Aires", "Córdoba", "Santa Fe", "Mendoza", "Entre Ríos", "La Pampa", "Neuquén", "Chubut", "Tierra del Fuego"]
      },
      {
        "nombre": ["Ciudad de México", "Estado de México", "Jalisco", "Nuevo León", "Puebla", "Veracruz", "Querétaro", "Chihuahua", "Baja California"]
      }
    ]

    this.countries = paises
    this.provinces = provincias
    // for (let i = 0; i < paises.length; i++) {
    //   const country = paises[i];

    //   this.countries = country.nombre
    //   console.log(this.countries);
    // }

    //console.log(this.countries);
    // aquí cargarías la lista de países y provincias desde tu fuente de datos
    // por ejemplo, podrías hacer una petición HTTP utilizando Axios o Fetch
    // y luego actualizar los arrays this.countries y this.provinces
  },
  methods: {
    updateProvinces() {
      // aquí filtrarías las provincias del país seleccionado y actualizarías
      // el array this.provinces con las provincias correspondientes
      // también podrías reiniciar el array this.cities para que no haya
      // ciudades seleccionadas de una provincia anterior
    },
    updateCities() {
      // aquí filtrarías las ciudades de la provincia seleccionada y actualizarías
      // el array this.cities con las ciudades correspondientes
    },
  },
}
</script>
  