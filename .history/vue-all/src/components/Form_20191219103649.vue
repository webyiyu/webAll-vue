<template>
    <form :model='model' :rules='rules'>
        <slot></slot>
    </form>
</template>

<script>
export default {
    privide:{
        
    },
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