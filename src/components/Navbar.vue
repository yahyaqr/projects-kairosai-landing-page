<template>
    <nav class="bg-[#0A0A0A] bg-opacity-80 backdrop-filter backdrop-blur-lg p-4 fixed w-full z-50 transition-all duration-300"
        :class="{ 'shadow-glow-sm': scrolled }">
        <div class="container mx-auto flex justify-between items-center px-4">
            <div class="text-2xl font-bold text-cyan-400">Kairos AI</div>
            <div class="relative">
                <!-- Display current active link -->
                <button @click="toggleDropdown"
                    class="text-sm font-medium tracking-wide text-white uppercase focus:outline-none">
                    {{ getActiveLinkName }}
                </button>
                <div v-if="dropdownOpen"
                    class="absolute right-0 mt-2 w-48 bg-[#0A0A0A] text-white rounded-md shadow-lg z-20">
                    <div v-for="item in navItems" :key="item.id">
                        <a :href="`#${item.id}`"
                            :class="['block px-4 py-2 text-sm hover:bg-gray-700 transition-colors relative group', { 'bg-gray-600': activeId === item.id }]"
                            @click="setActive(item.id); closeDropdown">
                            {{ item.name }}
                            <span
                                class="absolute left-0 right-0 bottom-0 h-0.5 bg-cyan-400 transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
                                :class="{ 'scale-x-100': activeId === item.id }"></span>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue';
defineProps(['scrolled'])

const navItems = [
    { id: 'hero', name: 'Introduction' },
    { id: 'how-it-works', name: 'How It Works' },
    { id: 'features', name: 'Features' },
    { id: 'use-cases', name: 'Use Cases' },
    { id: 'integrations', name: 'Integrations' },
    { id: 'pricing', name: 'Pricing' },
    { id: 'testimonials', name: 'Testimonials' },
    { id: 'faq', name: 'FAQ' },
    { id: 'cta', name: 'Contact' },
];

const activeId = ref('hero'); // Set the default active section
const dropdownOpen = ref(false);

const toggleDropdown = () => {
    dropdownOpen.value = !dropdownOpen.value; // Toggle dropdown visibility
};

const closeDropdown = () => {
    dropdownOpen.value = false; // Close dropdown
};

// Function to get the name of the active link
const getActiveLinkName = computed(() => {
    const activeItem = navItems.find(item => item.id === activeId.value);
    return activeItem ? activeItem.name : 'Menu'; // Fallback to 'Menu' if none found
});

const setActive = (id) => {
    activeId.value = id; // Update activeId on link click
    closeDropdown(); // Close dropdown when a link is clicked
};

// Function to check which section is in view
const checkActiveSection = () => {
    navItems.forEach(item => {
        const section = document.getElementById(item.id);
        if (section) {
            const rect = section.getBoundingClientRect();
            if (rect.top <= window.innerHeight / 2 && rect.bottom >= window.innerHeight / 2) {
                activeId.value = item.id; // Update activeId if section is in view
            }
        }
    });
};

onMounted(() => {
    window.addEventListener('scroll', checkActiveSection);
});

onBeforeUnmount(() => {
    window.removeEventListener('scroll', checkActiveSection);
});
</script>

<style scoped>
.shadow-glow-sm {
    box-shadow: 0 0 15px rgba(34, 211, 238, 0.2);
}
</style>
