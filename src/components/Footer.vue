<template>
    <footer class="bg-[#111111] py-16">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-xl font-bold text-cyan-400 mb-4">Kairos AI</h3>
                    <p class="text-gray-400">Revolutionizing workflow automation with AI</p>
                </div>
                <div v-for="(column, index) in footerColumns" :key="index">
                    <h4 class="font-semibold mb-4">{{ column.title }}</h4>
                    <ul class="space-y-2">
                        <li v-for="link in column.links" :key="link">
                            <a href="#" class="text-gray-400 hover:text-cyan-400 transition-colors">{{ link }}</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-800 mt-12 pt-8 text-center text-gray-400">
                <p>&copy; 2024 Kairos AI. All rights reserved.</p>
            </div>
        </div>
    </footer>
</template>

<script setup>
const footerColumns = [
    {
        title: 'Product',
        links: ['Features', 'Integrations', 'Pricing', 'FAQ']
    },
    {
        title: 'Company',
        links: ['About Us', 'Careers', 'Partners', 'News']
    },
    {
        title: 'Resources',
        links: ['Blog', 'Case Studies', 'Documentation', 'API']
    }
];
</script>

<style scoped>
/* Add any additional styles for Footer here */
</style>