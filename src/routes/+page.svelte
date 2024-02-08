<script>
    import logo from '$lib/assets/logo.svg';
    import easy from '$lib/assets/easy.svg';
    import openBook from '$lib/assets/open-book.svg';
    import responsive from '$lib/assets/responsive.svg';
    import copy from '$lib/assets/copy.svg';
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

        /**
        * @param {string} text
        */
        async function copyToClipboard(text) {
            await navigator.clipboard.writeText(text);
        }

</script>


<main class='container'>
    <section class='my-5 flex-full flex-col'>
        <img alt="The ovzocss logo" src={logo} />
        <h1 class="font-h1 text-center">OvzoCSS</h1>
        <h2 class="font-h4 text-center font-weight-regular">Minimalistic and clean CSS Library</h2>
        <div class='my-5'>
            <a href="/docs" class="button-primary text-none-decoration" >Docs</a>
            <a href="https://github.com/Sharqiewicz/ovzo-css" target='_blank' class="button-secondary text-none-decoration" >Github</a>
        </div>
    </section>

    <section class='my-5'>
        <ul class="features-container list-style-none ">
            {#each features as feature}
                    <li><Feature {...feature}/></li>
            {/each}
        </ul>
    </section>

    <section id="getStarted" class='my-5 flex-full flex-col'>
        <h3 class='font-h3'># Get Started</h3>
        <p>Use yarn:</p>
        <div class='relative code-snippet py-3 pr-6 pl-3'>
                <code><span class='text-primary'>yarn</span> add ovzocss</code>
                <button on:click={() => copyToClipboard('yarn add ovzocss')} type='button' class='button-no-styles absolute-right flex-full'><img src={copy} alt='Copy yarn add ovzocss' /></button>
        </div>

        <p>Use npm:</p>
        <div class='relative code-snippet py-3 pr-6 pl-3'>
            <code><span class='text-primary'>npm</span> install ovzocss</code>
            <button on:click={() => copyToClipboard('npm install ovzocss')} type='button' class='button-no-styles absolute-right flex-full'><img src={copy} alt='Copy npm install ovzocss' /></button>
        </div>

        <p>Import ovzocss to your project:</p>
        <div class='relative code-snippet py-3 pr-6 pl-3'>
            <code><span class='text-primary'>import </span>"ovzocss"</code>
            <button on:click={() => copyToClipboard('import "ovzocss"')} type='button' class='button-no-styles absolute-right flex-full'><img src={copy} alt='Copy import ovzocss' /></button>
        </div>
    </section>
</main>
<footer class='flex flex-col justify-center align-center'>
    <p>© {currentYear} OvzoCSS</p>
    <p>Created by <a href='https://szarkiewicz.com' target='_blank' >Kacper Szarkiewicz</a></p>
    <p>MIT License</p>
</footer>
<style>

.text-primary{
    color: var(--color-dark-yellow);
}
.relative{
    position: relative;
}

.pr-6 {
    padding-right: 2.25rem;
}

.button-no-styles {
    background: transparent;
    border: 0;
    cursor: pointer;
}

.button-no-styles:active, .button-no-styles:hover{
    filter: brightness(0.1);
}

.absolute-right{
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
}

.code-snippet{
    background-color: #f4f4f4;
    border-radius: 0.5rem;
    margin-bottom: 1rem;
}

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