<template>
    <div class="article">
        <h1>{{ title }}</h1>

        <p>Published on {{ published }}</p>
        <p>Shares: {{shares}}</p>

        <p class="lead">{{ content }}</p>

        <app-author :author="author"></app-author>
        <!-- Receive event from child Social.vue component -->
        <social-sharing @articleWasShared="shared('Hello!', $event)"></social-sharing>
    </div>
</template>

<script>
    // import moment from 'moment';
    import Author from './Author.vue';
    import Social from './Social.vue';

    export default {
        data() {
            return {
                title: 'Sam\'s Components Experiment',
                published: new Date(),
                content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla accumsan eu erat ut scelerisque.',
                author: {
                    firstName: 'Sam',
                    lastName: 'Jin'
                },
                shares: 0
            };
        },
        methods: {
          shared (msg, event) {
            this.shares++
            console.log(msg);
            console.log(event);
          }
        },
        // filter: {
        //     moment: function (val) {
        //         return moment(val).format('MMMM Do YY')
        //     }
        // },
        components: {
            'app-author': Author,
            'social-sharing': Social
        }
    }
</script>