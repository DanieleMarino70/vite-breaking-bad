<script>
import {store} from "../data/store.js"
import CardMain from "./CardMain.vue"
import CardOptions from "./CardOptions.vue"

export default {
    data() {
        return {
            store,
            
            
        }
    },
    components: { CardMain, CardOptions },

    methods: {
        choseOption(selected){
            console.log(selected);
            store.optionChosed = selected;
        }
    }

}


</script>

<template>
    <main>
        <div class="container">
            <CardOptions @option="choseOption"/>
            <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5 g-3">
                <div class="count w-100">NUMERO DI CARTE</div>
                <CardMain v-for="card in store.cardsList" :pic="card.card_images[0].image_url"  :name="card.name" :type="card.type"/>
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
