<template>
    <section id="hero" class="pt-32 pb-20 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col lg:flex-row gap-12 items-center">
            <header class="relative pr-4 text-center lg:text-left">
                <h1 ref="headline" v-show="headlineVisible"
                    class="text-6xl  max-w-2xl font-bold mb-6 bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent">
                    Maximize Productivity,
                    <span>Minimize Costs </span>
                    <span class="text-cyan-400">with AI</span>
                </h1>
                <p class="text-xl mb-8 text-gray-400 max-w-2xl mx-auto">
                    Kairos AI helps conventional companies implement AI to speed up their business workflows, enabling
                    them to scale efficiently and enhance operational effectiveness.
                </p>
                <a href="#hire-us" aria-label="Get started with Kairos AI"
                    class="gradient-button text-black font-bold py-4 px-8 rounded-lg transition-all duration-300 transform hover:scale-105 inline-flex items-center space-x-3">
                    <span>Get Started</span>
                    <ArrowRight class="w-5 h-5" />
                </a>
            </header>

            <div class="relative md:max-w-md"> <!-- Adjust image size on large screens -->
                <div ref="hoverElement"
                    class="aspect-video lg:aspect-square bg-gray-800 rounded-lg overflow-hidden transform transition-transform duration-300"
                    @mousemove="handleMouseMove" @mouseleave="resetTransform" aria-label="3D interactive demo image">
                    <img src="https://espeo.eu/wp-content/uploads/2022/04/Green-tech-what-it-is-about-and-why-you-should-keep-an-eye-on-its-development-in-2022.jpg"
                        alt="Demonstration of AI technology in a business environment"
                        class="w-full h-full object-cover rounded-lg" />
                </div>
            </div>
        </div>

        <div class="container mx-auto mt-24 px-4">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
                <div v-for="stat in stats" :key="stat.value" class="text-center">
                    <div class="text-4xl font-bold text-white mb-2">{{ stat.value }}</div>
                    <div class="text-sm text-gray-500">{{ stat.label }}</div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ArrowRight } from 'lucide-vue-next';
import { ref, onMounted, onBeforeUnmount } from 'vue';

const hoverElement = ref(null);
const headlineVisible = ref(true);

// Handles the 3D rotation based on mouse position
const handleMouseMove = (event) => {
    const { offsetX, offsetY, target } = event;
    const { clientWidth, clientHeight } = target;

    // Calculate rotation based on mouse position
    const rotationX = ((offsetY - clientHeight / 2) / clientHeight) * 20;
    const rotationY = ((offsetX - clientWidth / 2) / clientWidth) * -20;

    hoverElement.value.style.transform = `perspective(1000px) rotateX(${rotationX}deg) rotateY(${rotationY}deg)`;
};

// Reset the 3D rotation when the mouse leaves the element
const resetTransform = () => {
    hoverElement.value.style.transform = "perspective(1000px) rotateX(0deg) rotateY(0deg)";
};

// Function to check screen size and toggle headline visibility
const checkScreenSize = () => {
    if (window.innerWidth < 1024) { // Below 1024px
        headlineVisible.value = true; // Show headline
    } else {
        headlineVisible.value = true; // Keep headline visible on large screens
    }
};

// Set initial visibility and add resize listener
onMounted(() => {
    checkScreenSize();
    window.addEventListener('resize', checkScreenSize);
});

// Clean up the event listener on component unmount
onBeforeUnmount(() => {
    window.removeEventListener('resize', checkScreenSize);
});

const stats = [
    { value: '38+', label: 'Active Projects' },
    { value: '24k', label: 'Lines of Code' },
    { value: '4.8/5', label: 'Customer Rating' },
    { value: '620+', label: 'API Integrations' }
];
</script>

<style scoped>
.aspect-video {
    aspect-ratio: 16 / 9;
    transform-style: preserve-3d;
    transition: transform 0.2s ease-out;
}

.aspect-square {
    aspect-ratio: 1;
    transform-style: preserve-3d;
    transition: transform 0.2s ease-out;
}

/* Gradient metallic button styles */
.gradient-button {
    background: linear-gradient(90deg, #ffffff, #a1a1a1, #ffffff);
    background-size: 200% 200%;
    animation: shine 1.5s infinite linear;
    position: relative;
    overflow: hidden;
}

@keyframes shine {
    0% {
        background-position: 200% 0;
    }

    100% {
        background-position: 0 0;
    }
}
</style>
