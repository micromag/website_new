<template>
  <!--<div class="relative bg-grey-900 shadow">-->
   <div class="max-w-7xl mx-auto px-4 sm:px-6">
     <div class="flex justify-between items-center py-6 md:justify-start md:space-x-10">
       <div class="flex justify-start lg:w-0 lg:flex-1">
         <NuxtLink to="/">
           <span class="sr-only">Workflow</span>
           <img class="h-8 w-auto sm:h-20" src="/logo.png" alt="Logo">
         </NuxtLink>
       </div>
       
       <div class="-mr-2 -my-2 md:hidden">
         <button type="button" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-red-500">
           <span class="sr-only">Open menu</span>
         </button>
       </div>

       <!-- Desktop Menu -->
       <nav class="hidden md:flex space-x-10">

         <NuxtLink to="/Magazines" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
           Magazines
         </NuxtLink>

         <NuxtLink to="/Contribute" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
           Contribute
         </NuxtLink>

         <NuxtLink to="/ContactUs" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
           Contact Us
         </NuxtLink>
       </nav>
       <!-- Desktop Menu END -->
     </div>
     
     <!-- Mobile Menu -->
     <div class="absolute top-0 inset-x-0 z-10 p-2 transition transform origin-top-right md:hidden">
       <div class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-gray-900 divide-y-2 divide-gray-50">
         <div class="pt-5 pb-6 px-5">
           <div class="flex items-center justify-between">
             <NuxtLink to="/">
               <img class="h-8 w-auto sm:h-10" src="/Logo.png" alt="Logo">
             </NuxtLink>
             <div class="-mr-2">
               <button type="button" @click="isOpen = !isOpen" class="bg-grey-900 rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-blue-500">
                 <span class="sr-only">Open menu</span>
                 <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                   <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                 </svg>
               </button>
               
               <transition
                 enter-active-class="duration-200 ease-out"
                 enter-class="opacity-0 scale-95"
                 enter-to-class="opacity-100 scale-100"
                 leave-active-class="duration-100 ease-in"
                 leave-class="opacity-100 scale-100"
                 leave-to-class="opacity-0 scale-95"
               >
                 <div v-show="isOpen" class="origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg">
                   <div class="rounded-md bg-gray-900 shadow-xs">
                     <div class="mt-6">
                       <nav class="grid gap-y-8">
                         <NuxtLink to="/Magazines" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 p-3">
                           Magazines
                         </NuxtLink>

                         <NuxtLink to="/Contribute" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 p-3">
                           Contribute
                         </NuxtLink>

                         <NuxtLink to="/ContactUs" class="text-base font-medium text-white hover:text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 p-3">
                           Contact Us
                         </NuxtLink>
                       </nav>
                     </div>
                   </div>
                 </div>
               </transition>
             </div>
           </div>
         </div>
       </div>
     </div>
   </div>
 <!--</div>-->
</template>

<script lang="ts">

export default {
  name: "Header",
  data: () => ({
    isOpen: false,
})
};
</script>