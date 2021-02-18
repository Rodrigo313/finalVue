<template>
    <div class="partido">
        <form class="formulario">
            <fieldset>
                <legend>Nuevo partido</legend>
                <select class="local">
                    <option value="0">Equipo local</option>
                </select>
            </fieldset>
        </form>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .formulario{
        margin-left: 500px;
        
    }
    .local{
        float: left;
    }
</style>