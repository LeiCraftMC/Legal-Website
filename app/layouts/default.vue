<script setup lang="ts">
import { useHead } from "nuxt/app";
import type { NavigationMenuItem } from "@nuxt/ui";

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

    <UHeader>
        <template #title>
            <span class="font-bold">LeiCraft_MC</span>
        </template>

        <UNavigationMenu :items="links" />
        
        <template #body>
            <UNavigationMenu :items="links" orientation="vertical" class="w-full" />
        </template>


    
    </UHeader>

    <UMain class="py-8">
        <UContainer>
            <div class="border-4 border-gray-300 p-6 rounded-lg">
                <slot />
            </div>
        </UContainer>
    </UMain>
    
</template>
