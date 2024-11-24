<template>
    <section id="how-it-works" class="py-32 relative bg-[#0C0C0C]">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">
                HOW
                <span class="text-cyan-400">KAIROS AI</span>
                WORKS
            </h2>
            <div class="grid md:grid-cols-3 gap-12">
                <div v-for="(step, index) in howItWorks" :key="index" class="text-center">
                    <div class="bg-[#111111] rounded-full w-20 h-20 flex items-center justify-center mx-auto mb-6">
                        <component :is="step.icon" class="w-10 h-10 text-cyan-400" />
                    </div>
                    <h3 class="text-xl font-bold mb-4">{{ step.title }}</h3>
                    <p class="text-gray-400">{{ step.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Zap, Code, BarChart } from 'lucide-vue-next'

const howItWorks = [
    {
        icon: Zap,
        title: 'Connect Your Systems',
        description: 'Easily integrate Kairos AI with your existing tools and platforms, or we\'ll create a custom mobile and desktop app tailored to your needs.'
    },
    {
        icon: Code,
        title: 'Configure AI Agents',
        description: 'Set up custom AI agents designed for your specific business processes, focusing on easing process and workflow integration.'
    },
    {
        icon: BarChart,
        title: 'Optimize & Scale',
        description: 'Monitor performance, gather insights, and continuously improve your workflows with our advanced analytics.'
    }
]
</script>

<style scoped>
/* Add any additional styles for HowItWorksSection here */
</style>