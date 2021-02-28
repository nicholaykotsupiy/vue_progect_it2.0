<template>
    <form method="post" class="text-center">
        <div class="bg-gray-300 my-6 py-6 w-1/3 mx-auto rounded-lg">
            <label>
                <input
                    type="text" 
                    placeholder="Feedback"
                    class="border p-1"
                    v-model="callbackValue"
                />
                <input
                    type="button"
                    value="Submit"
                    class="bg-blue-300 rounded-sm mx-2  px-4 py-1"
                    :class="{ 'cursor-pointer': !isEmptyInput }"
                    :disabled="isEmptyInput"
                    @click="clickHandler"
                    v-on:click="clearValue"
                />
            </label>
        </div>
    </form>
</template>

<script>
export default {
    data() {
        return {
            callbackValue: '',
            isEmptyInput: true
        }
    },
    methods: {
        clearValue () {
            this.callbackValue = ''
        }
    },
    computed: {
        clickHandler () {
            return this.$emit('output', {callbackValue: this.callbackValue})
        }
    },
    watch: {
        callbackValue () {
            if (this.callbackValue !== '') 
                this.isEmptyInput = false
            else 
                this.isEmptyInput = true
        }
    }
}
</script>