<template>
  <div class="font-display border-t">
    <div class="container mx-auto">
      <section class="text-gray-600 body-font mx-10">
        <div
          class="container mx-auto flex py-24 md:flex-row flex-col items-center"
        >
          <div
            class="lg:flex-grow md:w-1/2 lg:pr-24 md:pr-16 flex flex-col md:items-start md:text-left mb-16 md:mb-0 items-center text-center"
          >
            <h1
              class="title-font sm:text-4xl uppercase text-3xl mb-4 font-medium text-gray-900"
            >
              IDEAL Power
              <br class="hidden lg:inline-block" />About Us
            </h1>
            <p class="mb-8 leading-relaxed">
              Authorized Distributor- COMPUTER CITY TECHNOLOGIES LTD Computer
              City Technologies Ltd is one of the largest ICT hardware
              distribution company as well as a solution provider in network and
              security space in Bangladesh. CCTL has been operating in
              Bangladesh ICT industry since 1999. Responding to the ICT needs of
              the country, CCTL was established with the goal to keep our
              generation updated with latest technology while assisting to
              secure the fastest access to the digital world. We have been able
              to set an example of excellence to our customers using the state
              of the art technology, quality products and dedicated pre-sales
              and post-sales support and service.
            </p>
            <div class="flex justify-center">
              <button
                class="inline-flex text-white bg-[#0095D9] border-0 py-2 px-6 focus:outline-none hover:bg-gray-600 rounded text-lg"
              >
                <NuxtLink to="/contact" class="block"> Contact Us </NuxtLink>
              </button>
            </div>
          </div>
          <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6">
            <img
              class="object-cover object-center rounded"
              alt="hero"
              src="/hq.jpg"
            />
          </div>
        </div>
      </section>
    </div>
  </div>
</template>
