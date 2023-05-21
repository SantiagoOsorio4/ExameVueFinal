<template>
    <div class="container" id="carreras">
        <h1>Categories List</h1>
        <table class="table">
                        <thead>
                            <tr>
      <th scope="col">Carreras</th>
    </tr>
  </thead>
  <tbody>
    <tr tr v-for="carrera in carreras">
      <td>{{$carreras.Nom_Car}}</td>
    </tr>
  </tbody>
</table>
    </div>
    </template>
    
    <script>
    import axios from 'axios'
    
    
    export default{
    
        name: 'carreras',
        data(){
            return{
                carreras: []
            }
        },
        mounted() {
            axios.get('http://127.0.0.1:8000/api/carreras').then(response => {this.carreras = response.data.carreras;
            });
        },
    
    }
    
    </script>