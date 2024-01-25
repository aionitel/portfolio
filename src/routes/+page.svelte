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
    <h1
        class="fixed text-white top-1/3 sm:top-1/2 font-peralta sm:text-6xl text-5xl text-center font-inconsolata"
    >
        Alex Ionitel's Homepage on the Interwebs
    </h1>
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

<!-- Sub Section -->
<div class="h-screen bg-white flex justify-between"></div>
