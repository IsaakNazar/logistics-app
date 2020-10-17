<template>
  <div class="contact">
    <div class="contact-box">
      <h1 class="contact-title">Contact Us</h1>
      <form>
        <InputText
          placeholder="Name"
          v-model="form.name"
        />
        <InputText
          placeholder="Email"
          v-model="form.email"
        />
        <InputText
          placeholder="Message"
          v-model="form.message"
        />
        <ButtonPrimary title="Contact Us"/>
      </form>
    </div>

    <div class="contact-info">
      <div class="contact-title">Tel:</div>
      <div class="contact-value">+1 (44) 123-45-67</div>
      <div class="contact-title">e-mail:</div>
      <div class="contact-value">info@yoursite.com</div>
      <div class="contact-title">website:</div>
      <div class="contact-value">www.example.com</div>
    </div>
  </div>
</template>

<script>
  import ButtonPrimary from './Button-Primary'
  export default {
    name: 'ContactUs',
    components: {
      ButtonPrimary,
      InputText: () => import('./Input-Text')
    },
    data: () => ({
      form: {
        name: '',
        email: '',
        message: ''
      }
    })
  }
</script>

<style scoped>
.contact {
  background: #3c414c;
  text-align: center;
  padding: 100px 0;
  color: white;
}

  .contact-box {
    max-width: 500px;
    margin: 0 auto;
  }

  .contact-info {
    margin-top: 50px;
    display: inline-grid;
    grid-template-columns: 100px max-content;
    grid-gap: 5px 0;
    text-align: initial;
  }

  .contact-title {
    color: #e0e4e7;
  }
  .contact-value {
    color: #5192b3
  }
</style>
