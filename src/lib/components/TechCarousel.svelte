<script lang="ts">
    import Carousel from "./Carousel.svelte";

    const images: string[] = [
        "https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Flogos-download.com%2Fwp-content%2Fuploads%2F2016%2F09%2FReact_logo_logotype_emblem.png&f=1&nofb=1&ipt=fe5653cf5986423db67a53f42299bfa5cf551cee2062aa2120e4afbd02cdd2cb&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.icon-icons.com%2Ficons2%2F2699%2FPNG%2F512%2Ftailwindcss_logo_icon_167923.png&f=1&nofb=1&ipt=c7649347a2e4dbc86bc9cec0e8e2268c6a3449035ddaf6a9f8f5efde4a9230e1&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.pinclipart.com%2Fpicdir%2Fbig%2F35-353932_bootstrap-bootstrap-4-logo-png-clipart.png&f=1&nofb=1&ipt=517154c63ae477c1f68551e773cfb446df7c26ddb2c41b8cd0f763cb0b7a2e65&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fngts-eg.com%2Fwp-content%2Fuploads%2F2020%2F01%2Fnodejs_logo.png&f=1&nofb=1&ipt=b626b1982ed5bf1eccfb561ae6088be9c19aa645bdfc98530cc566c064cc46ae&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogonoid.com%2Fimages%2Fsass-logo.png&f=1&nofb=1&ipt=026d8a7293a4e844a990b012b88b3e54a53b6208d2e1284d56b890385c1bf9f8&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fvectorified.com%2Fimages%2Fexpress-js-icon-20.png&f=1&nofb=1&ipt=a40ba7711141dc950950365b237f489d6462a6077c247774394de503905806d1&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.freebiesupply.com%2Flogos%2Flarge%2F2x%2Fpostgresql-logo-png-transparent.png&f=1&nofb=1&ipt=2cf0676115163ce67bc1c25540f8ae00e18a6794c471aba7c3105d005839ce16&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmiro.medium.com%2Fmax%2F2400%2F1*xQCjgB2DVqhtqGoGw9E6TQ.png&f=1&nofb=1&ipt=5e3f1f356b5eae3efff84bae5b3017ffb89e78211947f88f96bd19d7d2cae938&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn4.iconfinder.com%2Fdata%2Ficons%2Flogos-and-brands%2F512%2F97_Docker_logo_logos-1024.png&f=1&nofb=1&ipt=7aa364758a53c463e2454df7ea249fe6e8a480ca46a67320fe890d7cf6b65428&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmiro.medium.com%2Fmax%2F1200%2F1*d9MXw4wPVrLXhgG6eaP-pg.png&f=1&nofb=1&ipt=634865e9469888b952c02afe726d8ad21d9a14269b4e41672487c1dc2af44890&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fbs-uploads.toptal.io%2Fblackfish-uploads%2Fskill_page%2Fcontent%2Flogo_file%2Flogo%2F6212%2FGraphQL_Logo.svg-490ae3deb7c0f056c849d7463fb8ab39.png&f=1&nofb=1&ipt=0f380a7b0e35c7b98d9bcaf34a0834725f3d95b3999047a3a8294ed52cb521ad&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fimg2.storyblok.com%2F600x0%2Ff%2F82408%2F301x301%2Fab47eaa34f%2Fapollo.png&f=1&nofb=1&ipt=98ca8f61369b52f5bf332bbe912e03628798ca70135eed4e570a260f5fb8a6e8&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fassets.stickpng.com%2Fimages%2F62c48bbdd884e8c372162223.png&f=1&nofb=1&ipt=ec784a0eda308e74eeaf179593965cea0d4a02f2f21f289af701c8d67a15c0e1&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpresentations.bltavares.com%2Fouvi-falar-de-rust%2Fferris.png&f=1&nofb=1&ipt=2c8434763f8e89c3e903a4228f68d38fe07f8235837272199825f7329aa6d873&ipo=images",
        "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fd2uusema5elisf.cloudfront.net%2Fbooks%2Ffullstack-rust%2Fimages%2Factix_logo.png&f=1&nofb=1&ipt=21ca73c0e002fdc83463381e675fa6c73129eb5280e6e6f0bc9e837ef21d65c6&ipo=images",
    ].sort(() => Math.random() - 0.5); // Shuffle images on load for random order.

    const size: number = 100;
</script>

<div>
    <Carousel autoplay={2000}>
        {#each images as image}
            <img src={image} height={size} width={size} alt="carousel-item" />
        {/each}
    </Carousel>
</div>
