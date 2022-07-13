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
                        placeholder=" Type Research Title"
                        type="text"
                    />
                </div>
            </div>

            <div class="w-full">
                <label for="search" class="text-lg">Authors</label>
                <div class="relative">
                    <Chips v-model="authors" separator="," />
                </div>
            </div>

            <label for="search" class="text-lg">Abstract</label>
            <ckeditor
                :editor="editor"
                v-model="editorData"
                :config="editorConfig"
            ></ckeditor>

            <div class="w-full">
                <label for="search" class="text-lg">Keywords</label>
                <div class="relative">
                    <Chips v-model="keywords" separator="," />
                </div>
            </div>

            <div class="pt-10 mt-10 border-t border-gray-200">
                <h2 class="text-lg font-medium text-gray-900">Published?</h2>

                <fieldset class="mt-4 mb-8">
                    <div class="relative">
                        <select
                            v-model="published"
                            name=""
                            id=""
                            class="block w-full py-2 pl-10 pr-3 text-lg placeholder-gray-500 bg-white border-gray-300 rounded-md shadow-md border-1 focus:outline-none sm:text-lg"
                        >
                            <option :value="true">Yes</option>
                            <option :value="false">No</option>
                        </select>
                    </div>
                </fieldset>
            </div>
            <div class="w-full" v-if="published">
                <label for="search" class="text-lg">Journal Name</label>
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
                        id="Journal-name"
                        name="Journal-name"
                        class="block w-full py-2 pl-10 pr-3 text-lg placeholder-gray-500 bg-white border-gray-300 rounded-md shadow-md border-1 focus:outline-none sm:text-lg"
                        placeholder=" Type Journal Name"
                        type="text"
                    />
                </div>
            </div>
            <div class="w-full" v-if="published">
                <label for="search" class="text-lg">Year</label>
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
                        id="year"
                        name="year"
                        class="block w-full py-2 pl-10 pr-3 mb-8 text-lg placeholder-gray-500 bg-white border-gray-300 rounded-md shadow-md border-1 focus:outline-none sm:text-lg"
                        placeholder=" Type Published Year"
                        type="text"
                    />
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
            authors: null,
            keywords: null,
            published: false,
        }
    },
    components: { Header },
}
</script>

<style></style>
