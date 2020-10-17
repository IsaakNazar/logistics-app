<template>
  <div>
    <input
      type="text"
      :value="value"
      :placeholder="placeholder"
      @input="updateValue($event.target.value)">
    <div class="error">
      <span v-if="required && submitted">Field is required</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Input-Text',
    props: {
      required: Boolean,
      value: {type: String, required: this.required},
      placeholder: String,
      submitted: Boolean
    },
    methods: {
      updateValue (value) {
        this.$emit('input', value)
      }
    }
  }
</script>

<style scoped>

  input {
    font-size: 20px;
    border: 1px solid #c7c9d9;
    border-radius: 3px;
    font-weight: 400;
    padding: 8px 12px;
    transition: all .2s;
    width: 100%;
  }

  .error {
    margin-top: 3px;
    min-height: 20px;
    font-size: 12px;
    color: red;
  }
</style>
