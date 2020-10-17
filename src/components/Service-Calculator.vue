<template>
  <div class="container">
    <div class="boxes">
      <img src="../assets/shippingboxes.jpg" alt="">
    </div>
    <div class="calculator">
      <h1>Service Calculator</h1>
      <form
        @submit="checkForm">
        <InputText
          placeholder="Distance, km"
          v-model="form.distance"
          v-bind:required="!form.distance"
          v-bind:submitted="submitted"
          />
        <InputText
          placeholder="Weight, kg"
          v-model="form.weight"
          v-bind:required="!form.weight"
          v-bind:submitted="submitted"
          />
        <div class="dimension">
          <InputText
            placeholder="Length, m"
            v-model="form.length"
            v-bind:required="!form.length"
            v-bind:submitted="submitted"
            />
          <InputText
            placeholder="Height, m"
            v-model="form.height"
            v-bind:required="!form.height"
            v-bind:submitted="submitted"
            />

          <InputText
            placeholder="Width, m"
            v-model="form.width"
            v-bind:required="!form.width"
            v-bind:submitted="submitted"
          />
        </div>
        <button>Submit</button>
      </form>
      <div v-if="result" class="delivery">Your delivery will cost {{result}}$</div>
    </div>
  </div>
</template>

<script>
import InputText from './Input-Text'

export default {
  name: 'Service-Calculator',
  components: {InputText},
  data: () => ({
    form: {
      distance: '',
      weight: '',
      length: '',
      height: '',
      width: ''
    },
    submitted: false,
    result: ''

  }),
  methods: {
    checkForm (e) {
      e.preventDefault()
      this.submitted = true
      if (!this.isValid()) {
        return
      }
      const {distance, weight, length, height, width} = this.form
      const volume = length * height * width
      this.result = (volume > weight)
        ? (distance * length * height * width * 50)
        : distance * weight
      this.clear()
    },
    isValid () {
      return Object.values(this.form).every(item => !!item)
    },
    clear() {
      this.form.distance = ''
      this.form.weight = ''
      this.form.length = ''
      this.form.height = ''
      this.form.width = ''
      this.submitted = false
    }
  }
}
</script>

<style scoped>
  .container {
    max-width: 1440px;
    margin: 100px auto;
    display: grid;
    grid-template-columns: max-content auto;
  }

  .calculator {
    max-width: 400px;
  }

  .dimension {
    display: grid;
    grid-template-columns: repeat(3, auto);
    grid-gap: 10px;
  }

  button {
    background: #c7c9d9;
    font-size: 20px;
    padding: 8px 16px;
    border: 1px solid grey;
    border-radius: 3px;
    cursor: pointer;
  }

  .delivery {
    font-size: 18px;
    color: #565867;
    margin: 20px 0;
  }
</style>
