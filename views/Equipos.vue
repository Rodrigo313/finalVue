<template>
    <div class="equipos">
        <h1>Equipos</h1>
        <table>
            <tr class="tdd" v-for="(equipos, index) in arrayEquipos" :key="index">
                <td> {{equipos.name}}</td>
            </tr>
            <tr>
              <JugadoresEquipos :nombreJugadores="variable"/>
            </tr>
        </table>
        <button type="submit">Nuevo jugador</button>
    </div>
</template>

<script>
import axios from "axios";
import JugadoresEquipos from '@/components/JugadoresEquipos.vue'
export default {
    data(){
        return{
            arrayEquipos:[],
            variable: ''
        }
    },
     created(){
        axios.get('http://localhost:3000/clubs')
        .then(response =>{
            this.arrayEquipos = response.data;
        } )
        .catch(response => alert("Errores: " + response.status));
    },
    name: 'Equipos',
    components:{
      JugadoresEquipos
    }
}
</script>

<style scoped>
</style>
