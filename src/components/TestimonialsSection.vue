<template>
    <section id="testimonials" class="py-32 relative bg-[#0C0C0C]">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">
                TRUSTED BY
                <span class="text-cyan-400">INDUSTRY LEADERS</span>
            </h2>

            <div class="grid md:grid-cols-3 gap-8">
                <div v-for="testimonial in testimonials" :key="testimonial.name"
                    class="bg-[#111111] rounded-xl p-8 transition-all duration-300 hover:scale-105">
                    <div class="flex items-center mb-6">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 30 30" width="30" height="30"
                            class="w-12 h-12 rounded-full mr-4">
                            <rect width="30" height="30" fill="#cccccc"></rect>
                        </svg>
                        <div>
                            <h4 class="font-semibold text-white">{{ testimonial.name }}</h4>
                            <p class="text-gray-400">{{ testimonial.position }}</p>
                        </div>
                    </div>
                    <p class="text-gray-400">{{ testimonial.quote }}</p>
                    <div class="flex text-cyan-400 mt-6">
                        <svg v-for="i in 5" :key="i" xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                            viewBox="0 0 24 24" fill="rgb(34 211 238)" stroke-linecap="round" stroke-linejoin="round"
                            class="lucide lucide-star w-5 h-5">
                            <path
                                d="M11.525 2.295a.53.53 0 0 1 .95 0l2.31 4.679a2.123 2.123 0 0 0 1.595 1.16l5.166.756a.53.53 0 0 1 .294.904l-3.736 3.638a2.123 2.123 0 0 0-.611 1.878l.882 5.14a.53.53 0 0 1-.771.56l-4.618-2.428a2.122 2.122 0 0 0-1.973 0L6.396 21.01a.53.53 0 0 1-.77-.56l.881-5.139a2.122 2.122 0 0 0-.611-1.879L2.16 9.795a.53.53 0 0 1 .294-.906l5.165-.755a2.122 2.122 0 0 0 1.597-1.16z" />
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Star } from 'lucide-vue-next'

const testimonials = [
    {
        name: 'Jane Doe',
        position: 'CTO, TechCorp',
        quote: 'Kairos AI transformed our customer support process, reducing response times by 70% and increasing customer satisfaction.'
    },
    {
        name: 'John Smith',
        position: 'Data Scientist, DataCo',
        quote: 'The custom AI agent developed by Kairos AI helped us automate our data analysis, saving us countless hours and improving accuracy.'
    },
    {
        name: 'Emily Johnson',
        position: 'CEO, InnovateNow',
        quote: 'Implementing Kairos AI was a game-changer for our business. We\'ve seen a 40% increase in operational efficiency.'
    }
]
</script>

<style scoped>
/* Add any additional styles for TestimonialsSection here */
</style>