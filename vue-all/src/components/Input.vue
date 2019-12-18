<template>
    <div>
        <!-- v-model 双向数据绑定 
            1、绑定value值
            2、监听input事件
         -->
         <input type="text" @input='onInput' :value="value"/>
    </div>
</template>

<script>
export default {
    name: 'KInput',
    props: ['value'],
    methods: {
        onInput (e) {
            let val = e.target.value;
            this.$emit('input', val);
        }
    },
}
</script>