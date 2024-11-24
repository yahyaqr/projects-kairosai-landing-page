<template>
    <section id="tech-stack" class="py-32 relative overflow-hidden">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-4 text-center">
                POWERFUL
                <span class="text-cyan-400">TECH STACK</span>
            </h2>
            <p class="text-center text-gray-400 mb-12 max-w-2xl mx-auto">
                Our tech stack is built on modern and robust technologies, enabling seamless integration and high
                performance across all applications.
            </p>
            <div class="tech-stack-wrapper">
                <!-- Single Row Moving from Right to Left -->
                <div class="moving-logos">
                    <div class="flex">
                        <img src="https://placeholder.pics/svg/15x15" alt="PostgreSQL Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="SQLite Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Cheerio Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Puppeteer Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="FastAPI Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Docker Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="AWS Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="GCP Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Python Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Node.js Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="PostgreSQL Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="SQLite Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Cheerio Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Puppeteer Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="FastAPI Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Docker Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="AWS Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="GCP Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Python Logo" class="logo">
                        <img src="https://placeholder.pics/svg/15x15" alt="Node.js Logo" class="logo">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
// No data specific to this section
</script>

<style scoped>
.tech-stack-wrapper {
    overflow: hidden;
    /* Ensure overflow is hidden */
    position: relative;
    /* Position relative to contain absolute children */
    height: 100px;
    /* Fixed height to match logo height */
}

/* Container for moving logos */
.moving-logos {
    position: absolute;
    display: flex;
    white-space: nowrap;
    /* Prevent line breaks */
    animation: move-left 20s linear infinite;
    /* Move from right to left */
}

/* Animation for moving left */
@keyframes move-left {
    0% {
        transform: translateX(0);
        /* Start fully visible on the left */
    }

    100% {
        transform: translateX(-100%);
        /* Move to off-screen left */
    }
}

/* Logo styling */
.logo {
    height: 100px;
    /* Set a height for the logos */
    margin: 0 10px;
    /* Add horizontal margin for spacing */
}
</style>
