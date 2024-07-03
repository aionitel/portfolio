<script lang="ts">
    import ferrisImage from "$lib/assets/waving_ferris.png";
    import eye from "$lib/assets/eye.png";
    import { onMount } from "svelte";

    const ferrisSize: number = 200;
    const eyeSize: number = ferrisSize / 6;

    let leftEye;
    let rightEye;

    // Helper function.
    function getAngleDeg(
        mouseX: number,
        mouseY: number,
        anchorX: number,
        anchorY: number,
    ) {
        const diffX = mouseX - anchorX;
        const diffY = mouseY - anchorY;

        const rad = Math.atan2(diffY, diffX);
        return (rad * 180) / Math.PI;
    }

    onMount(() => {
        const anchor = document.getElementById("ferris-image")!;
        const eyes = document.querySelectorAll(".eye");

        const rect = anchor.getBoundingClientRect();

        const anchorX = rect.left + rect.width / 2;
        const anchorY = rect.top + rect.height / 2;

        // Eyes follow mouse pointer from coordinates.
        document.addEventListener("mousemove", (e) => {
            const mouseX = e.clientX;
            const mouseY = e.clientY;

            const angleDeg = getAngleDeg(mouseX, mouseY, anchorX, anchorY);

            eyes.forEach((eye) => {
                (eye as HTMLElement).style.transform =
                    `rotate(${180 + angleDeg}deg)`;
            });
        });
    });
</script>

<div class="relative">
    <img
        src={ferrisImage}
        width={ferrisSize}
        id="ferris-image"
        class="object-cover"
    />
    <div id="eyes" class="flex absolute top-[60px] left-[75px] object-cover">
        <img src={eye} class="eye" width={eyeSize} height={eyeSize} />
        <img src={eye} class="eye" width={eyeSize} height={eyeSize} />
    </div>
</div>
