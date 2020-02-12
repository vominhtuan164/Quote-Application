<template>
    <div class="row">
        <quote v-for="quote in quotes" :key="quote">{{quote}}</quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props: {
        quotes: Array
    },
    components: {
        quote: Quote,
    }
}
</script>

<style scoped>

</style>