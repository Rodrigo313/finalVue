<template>
    <div class="nuevoJugador">
        <form>
            <fieldset>
                <legend>Nuevo jugador</legend>
                <input class="nombre" type="text" placeholder="nombre jugador"><br><br>
                <input class="equipo" type="text" placeholder="equipo"><br><br>
                <input class="goles" type="number" placeholder="goles"><br><br>
                <button class="boton">Enviar</button>
            </fieldset>
        </form>
    </div>
</template>

<script>
import axios from 'axios'
import JugadoresEquipos from '@/components/JugadoresEquipos'
export default {
    components:{
        JugadoresEquipos
    }
}
</script>

<style scoped>
    .nombre{
        float: left;
    }
    .equipo{
        float: left;
    }
    .goles{
        float:left;
    }
    .boton{
        float: left;
    }
</style>