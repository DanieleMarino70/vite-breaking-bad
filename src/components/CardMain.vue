

<script>
import { store } from "../data/store.js"

export default {
    data() {
        return {
            store,
        }
    },
    props: {pic: String, name: String, type: String, selected: String}

}


</script>
<!-- v-if="atype == selected" -->
<template>
    <div class="col" v-if="type == store.optionChosed">
        <div class="p-3">
            <img :src="pic" alt="" class="img-fluid">
            <h6 class="text-white">{{ name }}</h6>
            <p>{{ type }}</p>
        </div>
    </div> 
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/_variables.scss" as *;
    .col {
        background-color: $bg-secondary;
        
        .p-3{
            background-color: $bg-primary;
            min-height: 450px;
        }
    }

</style>
