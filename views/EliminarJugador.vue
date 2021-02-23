<template>
    <div class="eliminacion">
        <form>
            <fieldset>
                <legend>Eliminar Jugador</legend>
                <select class="equipos" v-model="name">
                    <option :value="equipos.name" v-for="(equipos, nn) in arrayEquipos" :key="nn">{{equipos.name}}</option>
                </select><br><br>
                    <EliminarJug  class="jugadores" :nombreEquipo="name"></EliminarJug><br><br>
                <button class="boton" @click="borrarJugador(id)">Eliminar Jugador</button>
            </fieldset>
        </form>
    </div>
</template>

<script>
import axios from "axios";
import EliminarJug from '@/components/EliminarJug.vue'
export default {
    data(){
        return{
            arrayEquipos:[],
            arrayJugadores:[],
            id:'',
            name:'',
            team:'',
            scores:''

        }
    },
    methods:{
        equipos(){
            axios.get('http://localhost:3000/clubs')
            .then(response =>{
                this.arrayEquipos = response.data;
            } )
            .catch(response => alert("Errores: " + response.status));
        },
        jugadores(){
            axios.get('http://localhost:3000/players')
            .then(response =>{
                this.arrayJugadores = response.data;
            } )
            .catch(response => alert("Errores: " + response.status));
        },
        borrarJugador(id){
            axios.delete("http://localhost:3000/players/" + id);
        }
    },
    created(){
            this.equipos();
            this.jugadores();
    },
    components:{
        EliminarJug
    }
}
</script>

<style scoped>
    .equipos{
        float: left;
    }
    .jugadores{
        float: left;
    }
    .boton{
        float: left;
    }
</style>