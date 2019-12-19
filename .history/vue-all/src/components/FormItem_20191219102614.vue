<template>
    <div>
        <label for="">{{label}}</label>
        <div>
            <slot></slot>
            <p v-if="errorStatus">{{errorMessage}}</p>
        </div>
    </div>
</template>

<script>
import Schema from 'async-validator';
export default {
    props: ['label','prop'],
    data(){
        return {
            errorMessage: '',
            errorStatus: true,
        }
    },
    mounted() {
        this.$on('validate',this.validator)
    },
    methods: {
        validator() {
            // console.log(this.label)
            let schema = new Schema({});
        },
    }
}
</script>