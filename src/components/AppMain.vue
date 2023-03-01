<script>
import {store} from "../data/store.js"
import CardMain from "./CardMain.vue"

export default {
    data() {
        return {
            store,
            selected: "",
        }
    },
    components: { CardMain }

}


</script>

<template>
    <main>
        <div class="container">
            <select name="" id="" class="mt-5 mb-5" v-model="selected">
                <option disabled value="">Scegli tipo di carta</option>
                <option value="Alien">Alien</option>
            </select>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-3">
                <div class="count w-100">NUMERO DI CARTE</div>
                <CardMain v-for="card in store.cardsList" :pic="card.card_images[0].image_url"  :name="card.name" :atype="card.archetype" :selected="selected"/>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/_variables.scss" as *;

.count {
    background-color: black;
    color: white;
    line-height: 50px;
    
}
.row{
    background-color: $bg-secondary;
    border: 25px solid $bg-secondary;
}
</style>
