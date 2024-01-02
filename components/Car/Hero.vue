<template>
    <div class="
    relative 
    h-screen 
    w-100 
    bg-no-repeat bg-cover bg-bottom 
    bg-[url('https://carconfigurator.ferrari.com/rt-assets/data/cars/sf90stradale/ui/splashpage.jpg')]
    ">
            <div class="z-10 absolute w-full h-full flex justify-center items-center">
                <div class="text-center w-1/2">
                    <h1 class="text-8xl font-serif mb-1 text-white">Find your Drive</h1>
                    <!-- Home search Bar -->
                    <div
                        class="font-serif text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
                        <input type="text" v-model="city" 
                        class="py-2 px-5 w-full text-2xl rounded-full focus:outline-none "
                        :class="cityError ? 'border-red-500 border' : ''"
                            placeholder="search by city ...">
                        <button class="bg-sky-500 px-10"
                        @click="handleSearch">Search</button>
                    </div>
                    <!-- Home search Bar -->
                </div>

            </div>
            <div class="absolute w-full h-full bg-black opacity-50"></div>

        </div>
</template>

<script setup> 
const city = ref("")
const cityError = ref(false)
const handleSearch = () => {
    if(!city.value){
        cityError = true;
    }   
    navigateTo(`${city.value}/city/`)
}

</script>