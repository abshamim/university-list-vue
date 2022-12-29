<template>
    <div class="py-6">
        <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">
                    <div class="">
                        <h1 class="text-center font-bold text-3xl">University List in Bangladesh</h1><br>
                            <div>
                                <div class="flex flex-col text-center">
                                    <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
                                    <div class="py-2 inline-block min-w-full sm:px-6 lg:px-8">
                                        <div class="overflow-hidden">
                                        <table class="min-w-full">
                                            <thead class="border">
                                            <tr class="bg-emerald-500">
                                                <th scope="col" class="text-md font-medium border text-white px-6 py-4">
                                                University
                                                </th>
                                                <th scope="col" class="text-md font-medium border text-white px-6 py-4">
                                                Country
                                                </th>
                                                <th scope="col" class="text-md font-medium border text-white px-6 py-4">
                                                Website
                                                </th>
                                            </tr>
                                            </thead>
                                            <tbody v-for="university in universities" :key="university.id">
                                                <tr class="">
                                                    <td class="text-md text-black font-medium text-left border px-6 py-4 whitespace-nowrap">
                                                        {{ university.name }}
                                                    </td>
                                                    <td class="text-sm text-gray-900 font-normal border px-6 py-4 whitespace-nowrap" >
                                                        {{ university.country }}
                                                    </td>
                                                    <td class="text-sm text-gray-900 font-normal border px-6 py-4 whitespace-nowrap">
                                                        <span class="bg-violet-700 py-1 px-3 rounded text-white">
                                                            <a v-bind:href="university.web_pages[0]">Click Here</a>
                                                        </span>
                                                    </td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Home',
        data(){
            return {
                universities: []
            }
        },
        mounted() {
            fetch('http://universities.hipolabs.com/search?country=Bangladesh')
            .then(response => response.json())
            .then(kisuna => this.universities = kisuna)
        }
    }
</script>

<style scoped>
    *{
        font-family: 'Poppins', sans-serif;
    }
</style>