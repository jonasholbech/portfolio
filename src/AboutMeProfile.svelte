<script>
    import Tooltip from './Tooltip.svelte';
</script>
<section class="stats">
    <article>
        <h3>Bio</h3>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae commodi voluptatem quae rem necessitatibus! Tempore aliquid ea illo sequi ratione! Velit cumque deserunt necessitatibus nesciunt laborum, nihil consequatur dolore nemo.</p>
        <dl>
            <dt>Full Name:</dt>
            <dd>Jonas Fannikke Holbech</dd>
            <dt>Birth Date:</dt>
            <dd>August 6, 1978</dd>
            <dt>Email:</dt>
            <dd>jh@jonasholbech.dk</dd>
            <dt>Website:</dt>
            <dd>Looking at it</dd>
            <dt>Job:</dt>
            <dd>Frontender, Teacher &amp; Father</dd>
        </dl>
    </article>
    <article>
        <h3>Skills</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusamus possimus, voluptatibus sint deserunt alias perspiciatis. Hic explicabo beatae rem accusamus! Architecto saepe ut laudantium odit praesentium ipsa odio hic quia?</p>
        <ol>
            <li><Tooltip tooltip={"Vanilla JS"}>JavaScript</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>HTML</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>CSS</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>Git</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>SVG</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>PHP</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>SQL</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>NPM</Tooltip></li>
        </ol>
    </article>

    <article>
        <h3>Frameworks</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusamus possimus, voluptatibus sint deserunt alias perspiciatis. Hic explicabo beatae rem accusamus! Architecto saepe ut laudantium odit praesentium ipsa odio hic quia?</p>
        <ol>
            <li><Tooltip tooltip={"Vanilla JS"}>React</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>Svelte</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>Vue</Tooltip></li>
            <li><Tooltip tooltip={"I have mostly worked with WordPress & Drupal. But have experience in many more. These days, mostly headless"}>CMS</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>XState</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>GSAP</Tooltip></li>
            <li><Tooltip tooltip={"Vanilla JS"}>Firebase</Tooltip></li>
            
        </ol>
    </article>
    <article>
        <h3>Other shiny things</h3>
        <p>Tools and services that didn't fit anywhere else but really need to be mentioned</p>
        <ol>
            <li><Tooltip tooltip={"Vanilla JS"}>VS Code</Tooltip></li>
            <li><Tooltip tooltip={"Cloud functions and indentity!"}>Netlify</Tooltip></li>
            <li><Tooltip tooltip={"I love automation"}>Bash Scripts</Tooltip></li>
            <li><Tooltip tooltip={"A generous free tier with easy setup"}>MongoDB Atlas</Tooltip></li>
            <li><Tooltip tooltip={"The easiest bundler. Used when a CLI is not readily available"}>Parcel</Tooltip></li>
        </ol>
    </article>
    <article class="fullbleed">
        <button>Contact Me</button>
    </article>
</section>
<style>
    h3 {
        text-align: center;
    }
    dl {
        font-size:0.8rem;
    }
    dt {
        color:black;
        text-transform: uppercase;
        font-weight:bold;
    }
    p {
        max-width: 72ch;
        justify-self: center;
    }
    
    .stats {
        display:grid;
        gap:2rem;
    }
    ol {
        list-style-type:none;
        display:flex;
        flex-wrap: wrap;
        gap:1rem;
    }
    button {
        border: 3px solid #000;
        background:transparent;
        font-size:inherit;
        width: 100%;
        padding: 1rem;
        text-transform: uppercase;
        color:#000;
        font-weight: bold;
    }
    @media (min-width: 600px) {
        .stats {
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        }
    }
</style>