<template>
  <section class="contact">
    <h1>Hubungi Saya</h1>
    <form @submit.prevent="submitForm">
      <input type="text" v-model="form.name" placeholder="Nama Anda" required />
      <input type="email" v-model="form.email" placeholder="Email Anda" required />
      <textarea v-model="form.message" placeholder="Pesan Anda" required></textarea>
      <button type="submit">Kirim</button>
    </form>
    <p v-if="successMessage" class="success">{{ successMessage }}</p>
  </section>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
      successMessage: "",
    };
  },
  methods: {
    submitForm() {
      this.successMessage = `Terima kasih ${this.form.name}, pesanmu sudah terkirim!`;
      this.form.name = "";
      this.form.email = "";
      this.form.message = "";
    },
  },
};
</script>

<style scoped>
.contact {
  background: #111;
  color: white;
  padding: 3rem 1rem;
  text-align: center;
}

.contact h1 {
  font-size: 2.5rem;
  color: cyan;
  margin-bottom: 2rem;
}

form {
  max-width: 500px;
  margin: auto;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

input,
textarea {
  padding: 1rem;
  background: #222;
  border: 1px solid cyan;
  border-radius: 8px;
  color: white;
  font-size: 1rem;
}

button {
  padding: 1rem;
  background: cyan;
  color: black;
  font-weight: bold;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: white;
}

.success {
  margin-top: 1rem;
  color: lightgreen;
}
</style>
