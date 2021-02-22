<template>
    <div class="jugadores">
        <table>
            <tr class="tdd" v-for="(jugadores, index) in arrayJugadores" :key="index">
                <td> {{jugadores.name}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data(){
        return{
            nombre: ''
        }
    },
    props:[
      "nombreJugadores"
    ],
     created(){
        axios.get('http://localhost:3000/players?team')
        .then(response =>{
            this.arrayJugadores = response.data;
        } )
        .catch(response => alert("Errores: " + response.status));
    },
    envioJugadores(){
        let post = {
            nombre: this.nombre
        };
        axios.post("http://localhost:3000/players?team", post)
    },
    name: 'JugadoresEquipos',
}
</script>

<style scoped>

</style>