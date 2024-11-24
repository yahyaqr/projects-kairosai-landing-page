<template>
    <section id="use-cases" class="py-32 relative bg-[#0C0C0C]">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">
                PORTFOLIO
                <span class="text-cyan-400">SHOWCASE</span>
            </h2>
            <div class="grid md:grid-cols-2 gap-8">
                <div v-for="useCase in useCases" :key="useCase.title"
                    class="bg-[#111111] rounded-xl p-8 transition-all duration-300 hover:scale-105">
                    <component :is="useCase.icon" class="w-12 h-12 text-cyan-400 mb-6" />
                    <h3 class="text-xl font-bold mb-4">{{ useCase.title }}</h3>
                    <p class="text-gray-400">{{ useCase.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Drama, CheckCircle, Bot, MessageSquareText, Code, Wallpaper } from 'lucide-vue-next'

const useCases = [
    {
        icon: Drama, // Represents communication for Digital Talkshow
        title: 'Digital Talkshow Content Generator',
        description: 'Automate and optimize the creation of engaging content for your digital talkshows.'
    },
    {
        icon: CheckCircle, // Represents verification for Due Diligence
        title: 'Startup Success Due Diligence',
        description: 'Leverage thorough due diligence tools to evaluate startup potentials and mitigate risks.'
    },
    {
        icon: Bot, // Represents writing for LinkedIn content
        title: 'LinkedIn Ghostwriter',
        description: 'Enhance your professional presence with expertly crafted LinkedIn content tailored to your brand.'
    },
    {
        icon: MessageSquareText, // Represents journaling for WhatsApp Daily Journal
        title: 'WhatsApp Daily Journal',
        description: 'Streamline personal reflection and journaling through a convenient WhatsApp interface.'
    },
    {
        icon: Code, // Represents backend development for Backend + Dashboard Generator
        title: 'Backend + Dashboard Generator',
        description: 'Quickly develop robust backends and dashboards tailored to your specific business needs.'
    },
    {
        icon: Wallpaper, // Represents web design for Landing Page Generator
        title: 'Landing Page Generator',
        description: 'Create compelling landing pages effortlessly to boost your marketing efforts and conversions.'
    }
]
</script>

<style scoped>
/* Add any additional styles for UseCasesSection here */
</style>
