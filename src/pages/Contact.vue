<template>
  <section id="contact" class="py-16 bg-[#F5F5F4] px-6">
    <div class="max-w-3xl mx-auto text-center">
      <h2 class="font-display text-4xl text-[#333] mb-8">Kontak Kami</h2>
      <form @submit="sendEmail" class="flex flex-col gap-6 text-left">
  <input
    type="text"
    v-model="name"
    placeholder="Nama Anda"
    class="p-4 rounded-lg border focus:outline-none focus:ring-2 focus:ring-[#C4A484]"
  />
  <input
    type="email"
    v-model="email"
    placeholder="Email Anda"
    class="p-4 rounded-lg border focus:outline-none focus:ring-2 focus:ring-[#C4A484]"
  />
  <textarea
    rows="4"
    v-model="message"
    placeholder="Pesan Anda"
    class="p-4 rounded-lg border focus:outline-none focus:ring-2 focus:ring-[#C4A484]"
  ></textarea>
  <button
    type="submit"
    class="bg-[#C4A484] text-white py-3 rounded-lg hover:bg-[#b58d6e] transition duration-300"
  >
    Kirim Pesan
  </button>
</form>
    </div>
  </section>
</template>

<script setup>
import emailjs from 'emailjs-com'
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')

const sendEmail = (e) => {
  e.preventDefault()

  const templateParams = {
    from_name: name.value,
    from_email: email.value,
    message: message.value
  }

  emailjs
    .send(
      'service_ushs5ws',
      'template_0ljmufy',
      templateParams,
      'ZxJV4FAITi3uITcOS'
    )
    .then(
      (response) => {
        alert('Pesan berhasil dikirim!')
        name.value = ''
        email.value = ''
        message.value = ''
      },
      (error) => {
        alert('Gagal mengirim pesan.')
        console.error(error)
      }
    )
}
</script>
