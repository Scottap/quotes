<template>
    <div>
        <form>
            <div class="row">
                <div class="col-md-6 col-md-offset-3 col-sm-8 col-sm-offset-2 col-xs-6 col-lg-6">
                    <textarea class="form-control" cols="10" rows="10" v-model="quote"></textarea>
                </div>
                <div style="margin-top: 10px" class="col-md-6 col-md-offset-3 col-sm-8 col-sm-offset-2 col-xs-6 col-lg-6">
                    <button class="btn btn-primary" @click.prevent="newQuote">Add Quote</button>
                </div>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
      data() {
        return {
          quote: ''
        }
      },
      methods: {
        newQuote() {
          this.$emit('newQuote', this.quote)
          this.quote = ''
        }
      }
    }
</script>