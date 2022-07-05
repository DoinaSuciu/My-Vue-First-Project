<template>
  <main class="contact-page">
    <h1>Contact Us</h1>
    <form @submit.prevent="handleSubmit">
      <label for="name">
        Name:
        <br>
        <input id="name" type="text" placeholder="Enter your name">
      </label>
      <label for="phone">
        Phone:
        <br>
        <input id="phone" type="text" placeholder="Enter your phone number">
      </label>
      <label for="email">
        Email:
        <br>
        <input id="email" type="text" placeholder="Enter your email address">
      </label>
      <label for="message">
        Message:
        <br>
        <textarea id="message" placeholder="Enter you text..."></textarea>
      </label>

      <button>Submit</button>
    </form>
  </main>
</template>

<script>
export default {
  name: 'Contact',
  methods: {
    handleSubmit() {
      console.log('send details to server')
    }
  }
}
</script>

<style lang="scss">
.contact-page {
  form {
    width: 600px;
    margin: 0 auto;
    label{
      display: block;
      text-align: left;
      margin-bottom: 15px;
    }
    input, textarea {
      display: block;
      width: 100%;
      resize: none;
      font-family: Avenir, Helvetica, Arial, sans-serif;
      padding: 8px 5px;

    }
    button {
      display: block;
      align-self: center;
      margin: 50px auto 0;
      color: white;
      background-color: black;
      font-size: 18px;
      min-height: 40px;
      min-width: 100px;
      border: none;
      padding: 12px 24px;
      border-radius: 100px;
      cursor: pointer;
    }
  }
}

</style>
