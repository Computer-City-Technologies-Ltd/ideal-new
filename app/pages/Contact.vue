<script setup>
const customername = ref(null);
const email = ref(null);
const message = ref(null);
const honeyPot = ref(false);
const showThanks = ref(false);

const sendMail = async () => {
  try {
    const response = await $fetch("https://submit-form.com/hPy0xsit", {
      method: "POST",
      body: {
        name: customername.value,
        email: email.value,
        message: message.value,
        _honeypot: honeyPot.value,
      },
    });

    console.log(response);
    showThanks.value = true;
  } catch (error) {
    console.error(error);
  }
};

const toggleThanks = () => {
  showThanks.value = !showThanks.value;
};
</script>

<template>
  <div class="font-display border-t">
    <Sidemenu class="hidemobile" />
    <div class="mx-10">
      <section class="text-gray-600 body-font relative">
        <div class="pt-8 flex justify-center">
          <h2 class="lg:text-4xl text-2xl">Contact Us</h2>
        </div>
        <div class="flex justify-center">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-12 w-12"
            fill="none"
            viewBox="0 0 24 24"
            stroke="#0095D9"
            stroke-width="2"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M18 12H6" />
          </svg>
        </div>
        <div class="container px-5 py-2 mx-auto">
          <div class="lg:w-1/2 md:w-2/3 mx-auto">
            <p class="leading-normal my-5">
              75-76, B.S. Bhaban, 3rd Floor Laboratory Road Dhaka-1205,
              Bangladesh Tel: +88029612629-30.
            </p>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>
