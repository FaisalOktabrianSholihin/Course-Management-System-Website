<script lang="ts">
    import { page } from "$app/stores"; // Import page store untuk mendapatkan URL
    import { goto } from "$app/navigation";
    import { onMount } from "svelte";

    export let y;

    function redirectToLogin() {
        goto("/login");
    }

    // Variabel untuk cek halaman login
    let showHeader = true;

    $: {
        const currentPath = $page.url.pathname;
        showHeader = currentPath !== "/login" && currentPath !== "/register"; // Contoh: sembunyikan di halaman login dan register
    }
</script>

{#if showHeader}
    <header
        class={"sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-b border-solid " +
            (y > 0
                ? " py-4 bg-blue-200"
                : " py-6 bg-transparent border-transparent")}
    >
        <h1 class="font-medium">
            <b class="font-extrabold poppins">E-Course</b>
        </h1>
        <div class="sm:flex items-center gap-4 hidden">
            <button
                class="blueShadow relative overflow-hidden px-5 py-2 group rounded-md bg-white text-slate-950"
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Daftar</h4>
            </button>

            <button
                class="blueShadow relative overflow-hidden px-5 py-2 group rounded-md bg-blue-900 text-white"
                on:click={redirectToLogin}
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Masuk</h4>
            </button>
        </div>
    </header>
{/if}
