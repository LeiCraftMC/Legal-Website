<script setup lang="ts">
import type { NavigationMenuItem } from "@nuxt/ui";
import LCMCIcon from "~/components/img/LCMCIcon.vue";

useSeoMeta({
    title: "Rechtliches | LeiCraft_MC",
    description: "Rechtliche Informationen und Hinweise zu LeiCraft_MC, deinem Anlaufpunkt für einfache und verständliche Erklärungen zu rechtlichen Themen.",
});

const links = [[
    {
        label: "Impressum",
        to: "/impressum",
        class: "font-bold text-lg",
    },
    {
        label: "Datenschutz",
        to: "/datenschutz",
        class: "font-bold text-lg",
    },
    {
        label: "Haftungsausschluss",
        to: "/haftung",
        class: "font-bold text-lg",
    },
    {
        label: "Cookie-Richtlinie",
        to: "/cookies",
        class: "font-bold text-lg",
    },
]] satisfies NavigationMenuItem[][];
</script>

<template>

    <div class="app-layout main-bg-color">

        <UHeader>
            <template #title>
                <NuxtLink to="/" :class="`flex items-center gap-1.5`">
                    <LCMCIcon class="w-10 h-10" />
                    <span class="text-lg font-semibold">
                        LeiCraft_MC
                    </span>
                </NuxtLink>
            </template>

            <UNavigationMenu :items="links" />

            <template #body>
                <UNavigationMenu :items="links" orientation="vertical" class="w-full" />
            </template>



        </UHeader>

        <UMain class="py-8 main-content">
            <UContainer>
                <div class="border-4 border-gray-300 p-6 rounded-lg">
                    <slot />
                </div>
            </UContainer>
        </UMain>

        <UFooter class="mt-8 bg-neutral-900">
            <div class="text-sm text-slate-500 text-center">
                &copy; {{ new Date().getFullYear() }} LeiCraft_MC. All rights reserved.
            </div>
        </UFooter>

    </div>

</template>

<style scoped>
.app-layout {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.main-content {
    flex: 1;
}
</style>