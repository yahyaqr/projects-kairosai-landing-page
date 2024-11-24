<template>
    <section id="pricing" class="py-32 relative bg-[#0C0C0C]">
        <div class="container mx-auto px-4 flex flex-col md:flex-row justify-center">
            <!-- Star Rating on the Left -->
            <div class="flex flex-col items-center mb-8 md:mb-0 md:mr-8 md:items-end text-center md:text-left">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">
                    PRICING
                    <span class="text-cyan-400">THAT ADAPTS</span>
                </h2>
                <p class="text-gray-400 mb-6 text-lg md:text-base">Choose the perfect plan for your business needs</p>

                <div class="flex flex-wrap max-w-60 mb-8 justify-center">
                    <span v-for="star in 6" :key="star" @click="activateStars(star)"
                        class="cursor-pointer text-6xl md:text-8xl"
                        :class="activeStars >= star ? 'text-cyan-400' : 'text-gray-400'">
                        ★
                    </span>
                </div>
            </div>

            <!-- Plan Card on the Right -->
            <div class="md:max-w-xl md:w-96 md:ml-8">
                <div v-if="selectedPlan"
                    class="bg-[#111111] rounded-xl p-6 md:p-8 transition-all duration-300 hover:scale-105 flex-grow">
                    <div class="mb-6">
                        <h3 class="text-2xl md:text-xl font-bold mb-2">{{ selectedPlan.name }}</h3>
                        <p class="text-gray-400">{{ selectedPlan.description }}</p>
                    </div>
                    <div class="mb-6">
                        <span class="text-3xl md:text-4xl font-bold">${{ selectedPlan.price }}</span>
                        <span class="text-gray-400">/month</span>
                    </div>
                    <ul class="space-y-4 mb-6">
                        <li v-for="feature in selectedPlan.features" :key="feature" class="flex items-start space-x-3">
                            <Check class="w-5 h-5 text-cyan-400 flex-shrink-0 mt-1" />
                            <span class="text-gray-400">{{ feature }}</span>
                        </li>
                    </ul>
                    <a href="#" class="block w-full py-3 px-6 text-center rounded-lg transition-colors duration-300"
                        :class="selectedPlan.featured ? 'bg-cyan-500 hover:bg-cyan-400 text-black' : 'bg-[#222222] hover:bg-[#333333] text-white'">
                        Get Started
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, computed } from 'vue';
import { Check } from 'lucide-vue-next';

const plans = [
    {
        name: 'Starter Plan',
        description: 'For individuals and small teams',
        price: '0',
        featured: false,
        features: [
            'Up to 2 team members',
            'Basic AI automation tools',
            'Access to community support'
        ]
    },
    {
        name: 'Basic Plan',
        description: 'Perfect for small teams',
        price: '200',
        featured: false,
        features: [
            'Up to 5 team members',
            'Essential AI features',
            'Standard support',
            '3 projects'
        ]
    },
    {
        name: 'Growth Plan',
        description: 'For growing businesses',
        price: '400',
        featured: false,
        features: [
            'Up to 10 team members',
            'Enhanced automation capabilities',
            'Priority support',
            '5 projects'
        ]
    },
    {
        name: 'Pro Plan',
        description: 'Best for medium-sized companies',
        price: '600',
        featured: false,
        features: [
            'Up to 15 team members',
            'Advanced AI features',
            '24/7 support',
            'Unlimited projects'
        ]
    },
    {
        name: 'Business Plan',
        description: 'For larger organizations',
        price: '800',
        featured: false,
        features: [
            'Unlimited team members',
            'Custom AI solutions',
            'Dedicated account manager',
            'Unlimited projects and integrations'
        ]
    },
    {
        name: 'Enterprise Plan',
        description: 'For large enterprises',
        price: '1000',
        featured: false,
        features: [
            'All features included',
            'Tailored AI strategies',
            'Custom mobile and desktop app development',
            'Comprehensive support'
        ]
    }
];

const activeStars = ref(1);

// Watch the active stars and update the selected plan accordingly
const selectedPlan = computed(() => {
    switch (activeStars.value) {
        case 1: return plans[0]; // Starter Plan
        case 2: return plans[1]; // Basic Plan
        case 3: return plans[2]; // Growth Plan
        case 4: return plans[3]; // Pro Plan
        case 5: return plans[4]; // Business Plan
        case 6: return plans[5]; // Enterprise Plan
        default: return null; // No selection
    }
});

const activateStars = (count) => {
    activeStars.value = count;
};
</script>

<style scoped>
/* Add any additional styles for PricingSection here */
</style>
