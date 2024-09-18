<template>
    <div class="Cards" id="Cards">
        <div v-for="Pokemons in PokemonResponse" :key="Pokemons.id">
            <div class="carta"><img class="imagen" :src=Pokemons.imagen alt="">
                <h4>{{ Pokemons.nombre }}</h4>
                <div class="habilidades" :style="{ 'background-color': Pokemons.type_color }">
                    <span>{{ Pokemons.type_name }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    data() {
        return { PokemonResponse: [] }
    },
    methods: {
        cargarTarjetas: async function () {
            await this.axios.get('https://cobuses.com.co/APIV2/model/pokemon.php?dato=getallpokemon')
                .then(response => {
                    this.PokemonResponse = response.data;
                });
        }
    },
    mounted() {
        this.cargarTarjetas()
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.carta {
    width: 12rem;
    z-index: 1;
}
.Cards {
    width: 80%;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
}
.span {
    /* padding: 0 1px; */
    border-radius: 5px;
    flex-grow: 1;
    display: flex;
    justify-content: center;
}
.habilidades {
    display: flex;
    gap: 10px;
}
</style>