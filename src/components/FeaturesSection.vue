<template>
    <section id="features" class="py-32 relative">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">
                AN AI AUTOMATION TOOL
                <br />
                <span class="text-cyan-400">MADE FOR ENTERPRISES</span>
            </h2>

            <div class="grid md:grid-cols-2 gap-8 mx-auto">
                <div v-for="feature in features" :key="feature.title" class="relative group">
                    <div
                        class="bg-[#111111] rounded-xl overflow-hidden transition-transform duration-300 group-hover:scale-[1.02]">
                        <div class="px-8 pt-8">
                            <h3 class="text-xl font-bold mb-4">{{ feature.title }}</h3>
                            <p class="text-gray-400 mb-8">{{ feature.description }}</p>
                        </div>
                        <img :src="`https://placeholder.pics/svg/600x100`" alt="Feature Screenshot"
                            class="w-full object-cover rounded-b-lg shadow-2xl" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const features = [
    {
        title: 'Intelligent Process Automation',
        description: 'Our AI understands complex workflows and automates them with precision and efficiency.'
    },
    {
        title: 'Advanced Analytics Dashboard',
        description: 'Gain deep insights into your operations with our comprehensive analytics suite.'
    },
    {
        title: 'Natural Language Processing',
        description: 'Leverage cutting-edge NLP to automate communication and data extraction tasks.'
    },
    {
        title: 'Customizable AI Agents',
        description: 'Create and train AI agents specific to your unique business needs and processes.'
    }
];
</script>

<style scoped>
img {
    display: block;
    height: 50%;
}
</style>
