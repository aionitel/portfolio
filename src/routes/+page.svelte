<script lang="ts">
    import Typewriter from "svelte-typewriter";
    import { cascade } from "svelte-typewriter";
</script>

<svelte:head>
    <title>Alex Ionitel</title>
</svelte:head>
<div class="flex-row overflow-hidden relative z-0 text-white h-screen">
    <video
        class="flex h-full w-full object-cover"
        autoPlay
        muted
        loop
        playsInline
    >
        <source src="https://i.imgur.com/AAq8AGQ.mp4" />
    </video>
    <div
        class="z-10 inset-0 absolute flex justify-center mx-auto text-7xl hover:cursor-pointer top-3/4 h-12"
        on:click={() =>
            window.scrollTo({ top: screen.height - 50, behavior: "smooth" })}
    >
        <img
            src="https://cdn-icons-png.flaticon.com/512/271/271228.png"
            class="rotate-90 invert"
            alt="down-arrow"
        />
    </div>
</div>
<div class="bg-white h-screen" />
