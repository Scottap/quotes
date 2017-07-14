<template>
    <div>
        <div v-for="(quote, index) in quotes">
            <div class="col-md-4 col-lg-3 col-sm-6" @click="deleteQuote(index)">
                <div class="panel panel-default quote">
                    <div class="panel-body">
                        {{ quote }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import {eventBus} from '../../main'
    export default {
      props: ['quotes'],
      methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index)
        }
      }
    }
</script>

<style>
    .quote {
        font-family: 'Arizonia', cursive;
        font-size: 2.4em;
        -webkit-transition: ease-in-out 0.4s;
        -moz-transition: ease-in-out 0.4s;
        -ms-transition: ease-in-out 0.4s;
        -o-transition: ease-in-out 0.4s;
        transition: ease-in-out 0.4s;
        cursor: pointer;
    }
    .quote:hover {
        font-size: 2.4em;
        background-color: #D32F2F;
        color: white;
    }
</style>