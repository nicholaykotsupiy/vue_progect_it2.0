<template>
    <div class="text-center bg-gray-300 w-1/3 mx-auto py-4 rounded-lg text-lg my-2">
        <span><slot /> </span>
        <span>{{ title }}</span>
        <div class="text-sm text-gray-600">{{ sign }}</div>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: false
        }
    },
    inject: ['sign']
}
</script>