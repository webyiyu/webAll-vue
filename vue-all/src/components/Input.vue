<template>
    <div>
        <!-- v-model 双向数据绑定 
            1、绑定value值
            2、监听input事件
         -->
         <input :type="type" @input='onInput' :value="value"/>
    </div>
</template>

<script>
export default {
    name: 'KInput',
    props: {
        value: {
            type: String,
            default: '',
        },
        type: {
            type: String,
            default: 'text',
        },
    },
    methods: {
        onInput (e) {
            let val = e.target.value;
            this.$emit('input', val);
            this.$parent.$emit('validate');
        }
    },
}
</script>