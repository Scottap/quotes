<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes">
            <h1>Quotes to remember</h1>
        </app-header>
        <hr>
        <app-quoter @newQuote="newQuote"></app-quoter>
        <hr>
        <app-quotes :quotes="quotes"></app-quotes>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import {eventBus} from './main'
    import Header from './components/Shared/Header.vue'
    import Quoter from './components/Quo/Quoter.vue'
    import Quotes from './components/Quo/Quotes.vue'
    import Footer from './components/Shared/Footer.vue'

    export default {
      data() {
        return {
          quotes: ['Hi! -Dog, 2011'],
          maxQuotes: 10
        }
      },
      components: {
        appQuotes: Quotes,
        appQuoter: Quoter,
        appHeader: Header,
        appFooter: Footer
      },
      methods: {
        newQuote(quote) {
          if (this.quotes.length >= this.maxQuotes) {
            alert("Please delete some quotes before adding more!")
          } else {
            this.quotes.push(quote)
          }
        },
        deleteQuote(index) {
          this.quotes.splice(index, 1)
        }
      }
    }
</script>

<style>
</style>
