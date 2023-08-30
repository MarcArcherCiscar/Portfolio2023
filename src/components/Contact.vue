<template>
  <Toast ref="toast" />
  <article class="contact active" data-page="contact">
    <header>
      <h2 class="h2 article-title">Contact</h2>
    </header>

    <section class="mapbox" data-mapbox>
      <figure>
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2478.8308834333694!2d-0.3762886846017689!3d39.469909479484045!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xd6047402ebe3251%3A0xb992b25e8e59590e!2sValencia%2C%20Spain!5e0!3m2!1sen!2sus!4v1630346408990!5m2!1sen!2sus" width="400" height="300" loading="lazy"></iframe>
      </figure>
    </section>

    <section class="contact-form">
      <h3 class="h3 form-title">Contact Form</h3>
      <form class="form" @submit.prevent="sendEmail">
        <div class="input-wrapper">
          <input type="text" class="form-input" placeholder="Full name" required v-model="fullname">
          <input type="email" class="form-input" placeholder="Email address" required v-model="email">
        </div>
        <textarea class="form-input" placeholder="Your Message" required v-model="message"></textarea>
        <button class="form-btn" type="submit">
          <i class="pi pi-send" style="font-size: 1.5rem"></i>
          <span>Send Message</span>
        </button>
      </form>
    </section>
  </article>
</template>

<script>
import emailjs from 'emailjs-com';
import { ref } from 'vue';

export default {
  data() {
    return {
      fullname: '',
      email: '',
      message: ''
    };
  },
  methods: {
    sendEmail() {
      emailjs.send('service_qlb7zzb', 'template_kghlz8c', {
        fullname: this.fullname,
        email: this.email,
        message: this.message,
      }, '0oN1hR1XH2f96Terh')
      .then((response) => {
        console.log('SUCCESS!', response.status, response.text);
        this.$refs.toast.add({severity:'success', summary: 'Success', detail: 'Email sent successfully'});
      }, (error) => {
        console.error('FAILED...', error);
        this.$refs.toast.show({severity:'error', summary: 'Error', detail: 'Failed to send email'});
      });
    },
  },
};
</script>

