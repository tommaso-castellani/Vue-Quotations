<template>
    <div class="row">
        <quote
                v-for="(quote, index) in quotes"
                @click.native="deleteQuote(index)"
        >
            {{ quote }}
        </quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    export default {
        name: "QuotesGrid",
        props: [
            'quotes'
        ],
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index)
            }
        },
        components: {
            Quote
        }
    }
</script>

<style scoped>
    div {
        margin: 50px;
    }
</style>