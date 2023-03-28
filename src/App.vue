

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      showModal: false,
      isModalVisible: false,
    };
  },

  methods: {
   
    showModal1() {
      
      this.isModalVisible = true;
      
    },
    closeModal() {
      this.isModalVisible = false;
    },
  }
}
</script>




<template>



<header> 
  <img alt="Inbank logo" class="logo" src="./assets/icons/vector.svg" width="47" height="47"  />
</header>


  <div class="overflow-hidden bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto grid max-w-2xl grid-cols-1 gap-y-16 gap-x-8 sm:gap-y-20 lg:mx-0 lg:max-w-none lg:grid-cols-2">
        <img src="./assets/YIN4xUBaqnk.jpg" alt="Product screenshot" class="rounded-xl shadow-xl ring-1 ring-gray-400/10 sm:w-[57rem] md:-ml-4 lg:-ml-0" width="536" height="638" />
        <div class="lg:pl-8 lg:pt-4">

          <div class="lg:max-w-lg">
            <h2 class="font-sans font-normal leading-8 text-xl text-tundora  text-center">Good news</h2>

            <p class="font-sans font-light leading-8 text-center text-lg border-b-[1px] pb-5 border-gray/gray5-500 text-tundora leading-32 text-gray-600 sm:text-2xl"> Your loan has been approved.</p>

            <div class="grid grid-cols-2 gap-x-8">
              <p class="mt-6 text-right text-sm leading-8 text-gray-500">Personal loan offer</p>
              <p class="mt-6 text-left text-lg leading-8 text-black-600 px-8">1,700,00 &#8364;</p> <!--This text should be added as an element (from components/numbers.vue) because this is dynamyc parameter for each client -->
              <p class="mt-6 text-right text-sm leading-8 text-gray-500">Loan period</p> 
              <p class="mt-6 text-lg leading-8 text-black-600 text-left px-8">36 months</p> <!--This text should be added as an element (from components/numbers.vue) because this is dynamyc parameter for each client -->
              <p class="mt-6 text-right text-sm leading-8 text-gray-500">Monthly paymaent</p>
              <p class="mt-6 text-lg leading-8 text-black-600 text-left px-8 ">95.27 &#8364;</p><!--This text should be added as an element (from components/numbers.vue) because this is dynamyc parameter for each client -->
              
              <p class="mt-6 text-right text-sm leading-8 text-gray-500">Interest rate</p>
              <p class="mt-6 text-lg leading-8 text-black-600 text-left px-8 ">12.90%</p><!--This text should be added as an element (from components/numbers.vue) because this is dynamyc parameter for each client -->
              <p class="mt-6 text-right text-sm leading-8 text-gray-500">Margin</p>
              <p class="mt-6 text-lg leading-8 text-black-600 text-left px-8 ">8,90%+ 6 months EURIBOR (0%)</p><!--This text should be added as an element (from components/numbers.vue) because this is dynamyc parameter for each client -->

              <div class="col-span-full border-t border-gray-[500]">
                <p class="mt-6 mb-6 font-light text-center text-lg leading-8 text-gray-500">&#x2713; Promo code applied</p>
              </div>

              
              <div class="col-span-full border-t border-gray-[500]"></div>
              <div class="text-right">
                  <button class=" mt-[32px] bg-red-[500] bg-transparent hover:bg-gray-200 focus:outline-none
                  focus:ring focus:border-red-[700] rounded shadow-sm py-4 
                  px-[24px] font-medium hover:border-transparent border border-purple-300
                  transition duration-[150ms]" type="button">View offer details</button>
              </div>
                <div>
                  
              
                    <button @click="showModal1" class="mt-[32px] bg-red-[500] bg-purple-800 hover:bg-blue-700 focus:outline-none
                    focus:ring focus:border-red-[700] rounded shadow-sm py-4 
                    px-[24px] font-medium text-white 
                    transition duration-[150ms]" type="button"  >Not interested</button>
                    <Modal v-show="isModalVisible" @close="closeModal"></Modal>
                 
                 
                   
                </div>



  

            </div>

            <dl class="mt-10 max-w-xl space-y-8 text-base leading-7 text-gray-600 lg:max-w-none">
              <div v-for="feature in features" :key="feature.name" class="relative pl-9">
                <dt class="inline font-semibold text-gray-900">
                  <component :is="feature.icon" class="absolute top-1 left-1 h-5 w-5 text-indigo-600" aria-hidden="true" />
                  {{ feature.name }}
                </dt>
                {{ ' ' }}
                <dd class="inline">{{ feature.description }}</dd>
              </div>
            </dl>
          </div>
        </div>
      </div>
    </div>
  </div>
  

</template>

<style scoped>

.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1rem;
  }


  
.header {
  display: flex;
  align-items: center;
  padding: 1rem;
  background-color: #f5f5f5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
  margin-top: 22px;
}


@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

