<template>
  <div class="font-display">
    <header class="text-gray-600 body-font">
      <div
        class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center"
      >
        <NuxtLink
          to="/"
          class="flex title-font font-medium items-center text-gray-900 mb-4 md:mb-0"
        >
          <img src="/ideal-logo.png" class="w-24" />
        </NuxtLink>
        <nav
          class="md:mr-auto md:ml-4 md:py-1 md:pl-4 md:border-l md:border-gray-400 flex flex-wrap items-center text-base justify-center"
        >
          <NuxtLink
            to="/"
            class="mr-5 hover:text-white hover:bg-[#0095D9] px-4 py-2"
          >
            Home
          </NuxtLink>
          <NuxtLink
            to="/about"
            class="mr-5 hover:text-white hover:bg-[#0095D9] px-4 py-2"
          >
            About
          </NuxtLink>
          <NuxtLink
            to="/product"
            class="mr-5 hover:text-white hover:bg-[#0095D9] px-4 py-2"
            >Product</NuxtLink
          >
          <NuxtLink
            to="/contact"
            class="mr-5 hover:text-white hover:bg-[#0095D9] px-4 py-2"
            >Contact Us</NuxtLink
          >

          <NuxtLink
            to="/download"
            class="mr-5 hover:text-white hover:bg-[#0095D9] px-4 py-2"
            >Download</NuxtLink
          >
        </nav>
        <a href="https://www.comcitybd.com/brand/Ideal%20UPS">
          <button
            class="inline-flex items-center bg-gray-100 border-0 py-1 px-3 focus:outline-none hover:bg-gray-200 rounded text-base mt-4 md:mt-0"
          >
            See Pricing
            <svg
              fill="none"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              class="w-4 h-4 ml-1"
              viewBox="0 0 24 24"
            >
              <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
          </button>
        </a>
      </div>
    </header>
  </div>
</template>
