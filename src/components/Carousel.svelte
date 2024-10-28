<script>
    import { onMount, onDestroy } from "svelte";

    export let images;

    let currentIndex = 0;
    // @ts-ignore
    let interval;

    function next() {
        currentIndex = (currentIndex + 1) % images.length;
    }

    function prev() {
        currentIndex = (currentIndex - 1 + images.length) % images.length;
    }

    onMount(() => {
        interval = window.setInterval(next, 3000);
    });

    onDestroy(() => {
        // @ts-ignore
        clearInterval(interval);
    });
</script>

<div class="relative shadow-2xl grid place-items-center">
    <img
        src={images[currentIndex].src}
        alt={images[currentIndex].alt}
        class="object-cover z-[2] max-h-[70vh]"
    />
    <div class="absolute inset-0 flex justify-between items-center px-4">
        <button
            on:click={prev}
            class="text-white bg-black bg-opacity-50 p-2 rounded-full"
        >
            &#10094;
        </button>
        <button
            on:click={next}
            class="text-white bg-black bg-opacity-50 p-2 rounded-full"
        >
            &#10095;
        </button>
    </div>
</div>

<style>
    .carousel-controls button {
        background-color: rgba(0, 0, 0, 0.5);
        color: white;
        border: none;
        padding: 10px;
        border-radius: 50%;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .carousel-controls button:hover {
        background-color: rgba(0, 0, 0, 0.7);
    }
</style>
