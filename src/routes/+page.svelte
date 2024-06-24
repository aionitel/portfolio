<script lang="ts">
    import Typewriter from "svelte-typewriter";
</script>

<svelte:head>
    <title>Alex Ionitel</title>
</svelte:head>

<!-- Start Section -->
<div class="flex justify-center overflow-hidden relative h-screen">
    <video
        src="https://i.imgur.com/6ArY0RA.mp4"
        class="flex h-full w-full object-cover top-0 left-0 z-[-1] fixed"
        autoPlay
        muted
        loop
        playsInline
    />
    <Typewriter mode="loop">
        <div
            class="text-white h-screen flex items-center font-peralta text-7xl font-inconsolata"
        >
            <h1>Programming Enthusiast.</h1>
            <h1>Software Engineer.</h1>
            <h1>Hacker?</h1>
        </div>
    </Typewriter>
    <button
        class="flex justify-center mx-auto hover:cursor-pointer top-3/4 h-12 fixed"
        on:click={() =>
            window.scrollTo({
                top: screen.height,
                behavior: "smooth",
            })}
    >
        <img
            src="https://cdn-icons-png.flaticon.com/512/271/271228.png"
            class="rotate-90 invert"
            width={50}
            alt="down-arrow"
        />
    </button>
</div>

<!-- About Section -->
