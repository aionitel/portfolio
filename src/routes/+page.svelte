<script lang="ts">
    import BgVideo from "$lib/assets/bg.mp4";
</script>

<svelte:head>
    <title>Alex Ionitel</title>
</svelte:head>
<div class="flex justify-center overflow-hidden relative h-screen">
    <video
        src={BgVideo}
        class="flex h-full w-full object-cover"
        autoPlay
        muted
        loop
        playsInline
    />
    <h1
        class="absolute text-white top-1/2 font-peralta text-5xl text-center shadow-xl font-inconsolata"
    >
        Alex Ionitel's Homepage on the Interwebs
    </h1>
    <button
        class="absolute flex justify-center mx-auto hover:cursor-pointer top-3/4 h-12"
        on:click={() =>
            window.scrollTo({ top: screen.height, behavior: "smooth" })}
    >
        <img
            src="https://cdn-icons-png.flaticon.com/512/271/271228.png"
            class="rotate-90 invert"
            width={50}
            alt="down-arrow"
        />
    </button>
</div>
<div class="bg-white h-screen" />
