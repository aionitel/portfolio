<script lang="ts">
    import Typewriter from "svelte-typewriter";
    import { fade } from "svelte/transition";
    import { inview } from "svelte-inview";

    let isInView: boolean;
    const options: Options = {};

    if (isInView) {
        console.log("About text is in view!");
    }
</script>

<svelte:head>
    <title>Alex Ionitel's Home on the Internet</title>
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
    <div class="fixed">
        <Typewriter mode="loop">
            <div
                class="text-white h-screen flex items-center font-peralta text-8xl font-inconsolata"
            >
                <h1>Programming Enthusiast.</h1>
                <h1>Embedded Developer.</h1>
                <h1>Software Engineer.</h1>
                <h1>Aspiring Game Developer</h1>
                <h1>Hacker?</h1>
            </div>
        </Typewriter>
    </div>
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
<div class="bg-white relative">
    <div class="mx-auto md:w-1/2 w-2/3 pt-10">
        <h1 class="font-bold text-6xl">about</h1>
        <p class="font-inconsolata">
            Software engineer based out of Canada with three years of
            professional experience. Fluent in English and Russian. Passionate
            about (certain) programming languages. Proven track record for
            deivering web and mobile projects. For any important inquiries
            please contact
            <a
                class="hover:cursor-pointer text-blue-500 hover:opacity-[0.8] hover:underline"
                href="mailto:contact@alexiontel.dev"
                >contact@alexionitel.dev
            </a> or fill out the contact form below.
        </p>
    </div>
</div>

<!-- Work Section -->
<div class="bg-white relative">
    <div class="mx-auto md:w-1/2 w-2/3 pt-10">
        <h1 class="font-bold text-6xl">skills</h1>
        <div class="font-inconsolata flex justify-between">
            <div>
                <h2 class="mb-2">Languages:</h2>
                <p>
                    · English <br />
                    · Russian <br />
                    · Javascript/Typescript <br />
                    · HTML + CSS <br />
                    · Python <br />
                    · Go (Golang) <br />
                    · Rust <br />
                    · SQL (Structured Query Language) <br />
                    · JSON (Javascript Object Notation) <br />
                </p>
            </div>
            <div>
                <h2 class="mb-2">frontend</h2>
                <p>
                    · React <br />
                    · React Native <br />
                    · Redux <br />
                    · Svelte <br />
                    · NextJS <br />
                    · Vite <br />
                    · Webpack <br />
                    · Bootstrap <br />
                    · Tailwind CSS <br />
                    · SCSS <br />
                    · Figma <br />
                </p>
            </div>
            <div>
                <h2 class="mb-2">backend</h2>
                <p>
                    · NodeJS <br />
                    · Express <br />
                    · MySQL + PostgreSQL <br />
                    · Actix Web (Rust) <br />
                    · MongoDB <br />
                    · Redis <br />
                    · Stripe (Payments) <br />
                </p>
            </div>
        </div>
    </div>
</div>
