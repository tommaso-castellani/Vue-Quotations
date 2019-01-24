<template>
    <div class="container">
        <app-header :count="count" :countMax="countMax"></app-header>
        <new-quote @quoteAdded="pushQuote"></new-quote>
        <quotes-grid :quotes="quotes" @quoteDeleted="spliceQuotes"></quotes-grid>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import NewQuote from './components/NewQuote.vue';
    import QuotesGrid from './components/QuotesGrid.vue';

    export default {
        data() {
            return {
                quotes: [
                    'This is the first quote'
                ],
                countMax: 10,
                count: 1,
            }
        },
        methods: {
            pushQuote(quote) {
                if (this.quotes.length < 10) {
                    this.quotes.push(quote);
                    this.count += 1;
                }
                else {
                    alert('You can add more the 10 quotes. Delete some of that.')
                }

            },
            spliceQuotes(index) {
                this.quotes.splice(index, 1)
                this.count -= 1
            }
        },
        components: {
            appHeader: Header,
            NewQuote,
            QuotesGrid
        }
    }
</script>

<style>
</style>
