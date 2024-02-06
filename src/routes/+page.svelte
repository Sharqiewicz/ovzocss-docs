<script>
    import logo from '$lib/assets/logo.svg';
    import easy from '$lib/assets/easy.svg';
    import openBook from '$lib/assets/open-book.svg';
    import responsive from '$lib/assets/responsive.svg';
    import Feature from '$lib/feature.svelte';

    let features =  [
            {
                "svg": easy,
                "title": "Easy to Use",
                "description": "OvzoCSS is a lightweight and easy-to-use CSS library that provides a set of basic styles and components for web development."
            },
            {
                "svg": openBook,
                "title": "Open Source",
                "description": "OvzoCSS is open source and free to use. It is hosted on GitHub and can be installed via npm or CDN."
            },
            {
                svg: responsive,
                "title": "Responsive Design",
                "description": "OvzoCSS adapts to different screen sizes and devices, making it easy to create responsive web designs."
            }
        ];

        let currentYear = new Date().getFullYear();

</script>


<main class='container flex-full flex-col mt-5'>
        <img alt="The ovzocss logo" src={logo} class='mt-5'/>
        <h1 class="font-h1 text-center">OvzoCSS</h1>
        <h2 class="font-h4 text-center font-weight-regular">Minimalistic and clean CSS Library</h2>
        <div class='my-5'>
            <a href="/docs" class="button-primary text-none-decoration" >Docs</a>
            <a href="https://github.com/Sharqiewicz/ovzo-css" target='_blank' class="button-secondary text-none-decoration" >Github</a>
        </div>

    <ul class="features-container list-style-none">
        {#each features as feature}
                <li><Feature {...feature}/></li>
        {/each}
    </ul>

</main>
<footer class='flex flex-col justify-center align-center'>
    <p>© {currentYear} OvzoCSS</p>
    <p>Created by <a href='https://szarkiewicz.com' target='_blank' >Kacper Szarkiewicz</a></p>
    <p>MIT License</p>
</footer>
<style>
.features-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1rem;
    margin-left: 0 !important;
    padding-left: 0 !important;
}

@media (max-width: 1000px) {
  .features-container {
    grid-template-columns: 1fr;
  }
}
</style>