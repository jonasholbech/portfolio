<script>
    import Bio from "./Bio.svelte";
    import SkillList from "./SkillList.svelte";
    import skills from "./data/skills";
    import frameworks from "./data/frameworks";
    import shiny from "./data/shiny";
</script>

<style>
    h3 {
        text-align: center;
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
    <Bio />
    <SkillList {skills}>
        <h3>Skills</h3>
        <p>
            The core skills I use in my day to day work, or picked up along the
            way
        </p>
    </SkillList>

    <SkillList skills={frameworks}>
        <h3>Frameworks</h3>
        <p>
            I LOVE frameworks, and I love learning new frameworks. I'm pretty
            proficient in React, but leaning heavily against Svelte these days.
        </p>
    </SkillList>
    <SkillList skills={shiny}>
        <h3>Other shiny things</h3>
        <p>
            Tools and services that didn't fit anywhere else but really need to
            be mentioned
        </p>
    </SkillList>
    <button>Contact Me</button>
</section>
