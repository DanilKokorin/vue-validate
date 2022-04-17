<template>
  <div class="form-control" :class="{invalid: errors}">
        <label for="id">{{ label }}</label>
        <input 
            type="text" 
            :id="id" 
            :placeholder="placeholder"
            :value="modelValue"
            @input="onChange"
        >
        <small v-if="errors">{{ errors }}</small>
    </div>
</template>

<script>
export default {
    emits: ['update:modelValue'],
    props: {
        modelValue: String,
        placeholder: String,
        label: String,
        errors: String
    },
    methods: {
        onChange (event) {
            this.$emit('update:modelValue', event.target.value)
        }
    },
    data () {
        return {
            id: 'input-' + Math.random()
        }
    }
}
</script>

<style>

</style>