<template>
    <div>
        <slot></slot>
        <div>
            <div class="progress">
                <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                    {{ quoteCount }} / {{ maxQuotes }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      props: ['quoteCount', 'maxQuotes'],
      data() {
        return {
        }
      },
      methods: {
      }
    }
</script>

<style scoped>
    .meter {
        width: 100%;
        background-color: #ccc;
        color: black;
    }
    .meter > div {
        width: 10%;
        background-color: blue;
    }
</style>