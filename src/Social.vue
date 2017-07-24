<template>
    <button @click="share()" class="btn btn-primary">Share on Facebook</button>
</template>

<script>
    export default {
        data() {
            return {}
        },
        methods: {
          share () {
            // Emit pass event and event argument to parent component which is Article.vue in this case. 
            this.$emit('articleWasShared', {
                media: 'Facebook'
            })
          }
        }
    };
</script>

