<script>
    import Tooltip from "./Tooltip.svelte";
    import skills from "./data/skills";
</script>

<style>
    h3 {
        text-align: center;
    }
    dl {
        font-size: 0.8rem;
    }
    dt {
        color: black;
        text-transform: uppercase;
        font-weight: bold;
    }
    dd {
        margin-bottom: 0.5rem;
    }
    p {
        max-width: 72ch;
        justify-self: center;
    }

    .stats {
        margin-top: 1rem;
        display: grid;
        gap: 2rem;
    }
    ol {
        list-style-type: none;
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
    }
    button {
        border: 3px solid #000;
        background: transparent;
        font-size: inherit;
        width: 100%;
        padding: 1rem;
        text-transform: uppercase;
        color: #000;
        font-weight: bold;
        grid-column: 1/-1;
    }
    @media (min-width: 600px) {
        .stats {
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        }
    }
</style>

<section class="stats">
    <article>
        <h3>Bio</h3>
        <p>Some boring information as well as a way to contact me</p>
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
        <p>
            The core skills I use in my day to day work, or picked up along the
            way
        </p>
        <ol>
            {#each skills as skill (skill.tag)}
                <li>
                    <Tooltip tooltip={skill.desc}>{skill.tag}</Tooltip>
                </li>
            {/each}
        </ol>
    </article>

    <article>
        <h3>Frameworks</h3>
        <p>
            I LOVE frameworks, and I love learning new frameworks. I'm pretty
            proficient in React, but leaning heavily against Svelte these days.
        </p>
        <ol>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>React</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>Svelte</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>Vue</Tooltip>
            </li>
            <li>
                <Tooltip
                    tooltip={'I have mostly worked with WordPress & Drupal. But have experience in many more. These days, mostly headless'}>
                    CMS
                </Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>XState</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>GSAP</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>Firebase</Tooltip>
            </li>
        </ol>
    </article>
    <article>
        <h3>Other shiny things</h3>
        <p>
            Tools and services that didn't fit anywhere else but really need to
            be mentioned
        </p>
        <ol>
            <li>
                <Tooltip tooltip={'Vanilla JS'}>VS Code</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'Cloud functions and indentity!'}>
                    Netlify
                </Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'I love automation'}>Bash Scripts</Tooltip>
            </li>
            <li>
                <Tooltip tooltip={'A generous free tier with easy setup'}>
                    MongoDB Atlas
                </Tooltip>
            </li>
            <li>
                <Tooltip
                    tooltip={'The easiest bundler. Used when a CLI is not readily available'}>
                    Parcel
                </Tooltip>
            </li>
        </ol>
    </article>
    <button>Contact Me</button>
</section>
