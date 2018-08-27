<template>
    <div>
        <input type="text" v-model="message" autofocus/>
        <div>{{ message }}</div>
        <div>{{ myMessage1 }}</div>
        <div>{{ myMessage2 }}</div>
    </div>
</template>

<script lang="ts">
    import {Component, Watch, Vue} from 'vue-property-decorator'

    @Component({})
    export default class App extends Vue {
        message: string = 'change me'

        myMessage1: string = ''
        myMessage2: string = ''

        @Watch('message')
        update() {
            this.myMessage1 = this.message + ' (1)'
            this.myMessage2 = this.message + ' (2)'
        }
    }
</script>
