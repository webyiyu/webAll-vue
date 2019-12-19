<template>
    <form :model='model' :rules='rules'>
        <slot></slot>
    </form>
</template>

<script>
export default {
    props:{
        model:{
            type: Object,
            required: true,
        },
        rules:{
            type: Object,
        },
    }
}
</script>