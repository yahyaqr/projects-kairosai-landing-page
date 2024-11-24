<template>
    <section id="faq" class="py-32 relative">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">
                FREQUENTLY ASKED
                <span class="text-cyan-400">QUESTIONS</span>
            </h2>

            <div class="max-w-3xl mx-auto space-y-6">
                <div v-for="faq in faqs" :key="faq.question"
                    class="bg-[#111111] rounded-xl transition-all duration-300">
                    <button @click="faq.isOpen = !faq.isOpen"
                        class="w-full p-6 text-left flex justify-between items-center">
                        <span class="font-semibold">{{ faq.question }}</span>
                        <ChevronDown class="w-5 h-5 transform transition-transform duration-300"
                            :class="{ 'rotate-180': faq.isOpen }" />
                    </button>
                    <div v-show="faq.isOpen" class="px-6 pb-6">
                        <p class="text-gray-400">{{ faq.answer }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ChevronDown } from 'lucide-vue-next'
import { ref } from 'vue'

const faqs = ref([
    {
        question: 'What types of companies does Kairos AI target?',
        answer: 'We focus on small to medium companies owned by the younger generation, emphasizing digitalization and efficiency.',
        isOpen: false
    },
    {
        question: 'How does Kairos AI integrate with my current systems?',
        answer: 'Kairos AI can seamlessly integrate with your existing dashboard, or we can create a custom mobile and desktop application tailored to your needs.',
        isOpen: false
    },
    {
        question: 'What are the key use cases for Kairos AI?',
        answer: 'Our solutions are designed for content creation and AI business workflow integration, helping companies improve efficiency and productivity.',
        isOpen: false
    },
    {
        question: 'What support do you offer for different pricing plans?',
        answer: 'Support varies by plan, with community support for the Starter Plan, standard support for the Basic Plan, and 24/7 support for higher tiers.',
        isOpen: false
    },
    {
        question: 'Can I customize the AI agents to fit my specific needs?',
        answer: 'Yes, our AI agents are highly customizable to meet your unique business requirements and processes.',
        isOpen: false
    },
    {
        question: 'What results can I expect after implementing Kairos AI?',
        answer: 'Most clients start seeing tangible results within 2-4 weeks of implementation, with full impact usually evident after 2-3 months.',
        isOpen: false
    }
])
</script>

<style scoped>
/* Add any additional styles for FAQSection here */
</style>