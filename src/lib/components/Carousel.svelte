<script>
    import Siema from "siema";
    import { onMount, createEventDispatcher } from "svelte";

    export let perPage;
    export let loop = true;
    export let autoplay = 0;
    export let duration = 200;
    export let easing = "ease-out";
    export let startIndex = 0;
    export let draggable = true;
    export let multipleDrag = true;
    export let dots = true;
    export let controls = true;
    export let threshold = 20;
    export let rtl = false;
    let currentIndex = startIndex;

    let siema;
    let controller;
    let timer;

    const dispatch = createEventDispatcher();

    $: pips = controller ? controller.innerElements : [];
    $: currentPerPage = controller ? controller.perPage : perPage;

    onMount(() => {
        const setPerPage = () => {
            perPage = window.innerWidth < 1080 ? 1 : 8;
        };

        setPerPage();

        controller = new Siema({
            selector: siema,
            perPage: typeof perPage === "object" ? perPage : Number(perPage),
            loop,
            duration,
            easing,
            startIndex,
            draggable,
            multipleDrag,
            threshold,
            rtl,
            onChange: handleChange,
        });

        if (autoplay) {
            timer = setInterval(right, autoplay);
        }
        return () => {
            autoplay && clearInterval(timer);
            controller.destroy();
        };
    });

    export function isDotActive(currentIndex, dotIndex) {
        if (currentIndex < 0) currentIndex = pips.length + currentIndex;
        return (
            currentIndex >= dotIndex * currentPerPage &&
            currentIndex < dotIndex * currentPerPage + currentPerPage
        );
    }

    export function left() {
        controller.prev();
    }

    export function right() {
        controller.next();
    }

    export function go(index) {
        controller.goTo(index);
    }

    export function pause() {
        clearInterval(timer);
    }

    export function resume() {
        if (autoplay) {
            timer = setInterval(right, autoplay);
        }
    }

    function handleChange(event) {
        currentIndex = controller.currentSlide;
        dispatch("change", {
            currentSlide: controller.currentSlide,
            slideCount: controller.innerElements.length,
        });
    }

    function resetInterval(node, condition) {
        function handleReset(event) {
            pause();
            resume();
        }

        if (condition) {
            node.addEventListener("click", handleReset);
        }

        return {
            destroy() {
                node.removeEventListener("click", handleReset);
            },
        };
    }
</script>

<div class="relative justify-center align-middle">
    <div class="slides" bind:this={siema}>
        <slot />
    </div>
</div>
