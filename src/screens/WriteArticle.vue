<template>
    <main>
        <Header />
        <div id="app" class="flex-col px-8 m-auto space-y-8 max-w-7xl">
            <span class="w-full text-3xl font-bold text-center">
                Write Your Article
            </span>
            <div class="w-full">
                <label for="search" class="text-lg">Title of Research</label>
                <div class="relative">
                    <div
                        class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none"
                    >
                        <SearchIcon
                            class="w-5 h-5 text-gray-400"
                            aria-hidden="true"
                        />
                    </div>
                    <input
                        id="title"
                        name="title"
                        class="block w-full py-2 pl-10 pr-3 text-lg placeholder-gray-500 bg-white border-gray-300 rounded-md shadow-md border-1 focus:outline-none sm:text-lg"
                        placeholder=" Type name"
                        type="text"
                    />
                </div>
            </div>

            <div class="w-full">
                <label for="search" class="text-lg">Authors</label>
                <div class="relative">
                    <div
                        class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none"
                    >
                        <SearchIcon
                            class="w-5 h-5 text-gray-400"
                            aria-hidden="true"
                        />
                    </div>
                    <input
                        id="title"
                        name="title"
                        class="block w-full py-2 pl-10 pr-3 text-lg placeholder-gray-500 bg-white border-gray-300 rounded-md shadow-md border-1 focus:outline-none sm:text-lg"
                        placeholder=" "
                        type="text"
                    />
                </div>
            </div>

            <label for="search" class="text-lg">Abstract</label>
            <ckeditor
                :editor="editor"
                v-model="editorData"
                :config="editorConfig"
            ></ckeditor>

<div class="mt-6 grid grid-cols-4 gap-y-6 gap-x-4">
              <div class="col-span-20">
                <label for="card-number" class="block text-sm font-medium text-gray-700">Journal Name</label>
                <div class="mt-1">
                  <input type="text" id="journal-name" name="journal-name" autocomplete="cc-number" class="block w-full border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
                </div>
              </div>
              
            </div>
   
        
       <div class="mt-10 border-t border-gray-200 pt-10">
            <h2 class="text-lg font-medium text-gray-900">Published?</h2>

            <fieldset class="mt-4">
              <legend class="sr-only">Journal-name</legend>
              <div class="space-y-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-10">
                
                  <div class="flex items-center">
                    
                      <input id="credit-card" name="payment-type" type="radio" checked="" class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300">
                    <label for="credit-card" class="ml-3 block text-sm font-medium text-gray-700">
                      Yes
                    </label>
                  </div>
                
                  <div class="flex items-center">
                    
                      <input id="paypal" name="payment-type" type="radio" class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300">
                    <label for="paypal" class="ml-3 block text-sm font-medium text-gray-700">
                      No
                    </label>
                  </div>
                
                  
                
              </div>
              
            </fieldset>

            <div>
            .
            </div>
            
          </div>
   
    </div>
  
    </main>
</template>

<script>
import Header from '../components/Header.vue'
export default {
    data() {
        return {
            editor: ClassicEditor,
            editorData: '<p>Content of the editor.</p>',
            editorConfig: {
                // The configuration of the editor.
            },
        }
    },
    components: { Header },
}
</script>

<style></style>
