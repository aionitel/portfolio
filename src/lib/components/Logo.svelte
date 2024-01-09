<script lang="ts">
    import Logo from "$lib/assets/logo.png";

    let isHovered: boolean = false;

    function toggleHover() {
        isHovered = !isHovered;
    }

    function handleLogoClick() {
        window.scrollTo({ top: 0, behavior: "smooth" });
    }
</script>

<div
    class="flex justify-end top-2 z-[999] sticky"
    on:mousedown={handleLogoClick}
>
    <div
        on:mouseenter={toggleHover}
        on:mouseleave={toggleHover}
        class="absolute"
    >
        <img
            src={isHovered
                ? "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia3.giphy.com%2Fmedia%2Fv1.Y2lkPTc5MGI3NjExODNmMWFmOTJhZjg2ZDI5MmY4NjMyMDM5MmU1MzRhMTA5YzhiZWUxZiZjdD1z%2FdYyRWrXb9OpfYbhNY4%2Fgiphy.gif&f=1&nofb=1&ipt=6c939ca6b677cc42318d6a426fa787b2f809b6e9e923be1e99e32e7dc6c103e6&ipo=images"
                : Logo}
            width={100}
        />
    </div>
</div>
