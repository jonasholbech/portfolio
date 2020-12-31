<script>
    import Tooltip from "./Tooltip.svelte";
    export let skills;
</script>

<style>
    ul {
        list-style-type: none;
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
    }
</style>

<article>
    <slot />
    <ul>
        {#each skills as skill (skill.tag)}
            <li>
                <Tooltip tooltip={skill.desc}>{skill.tag}</Tooltip>
            </li>
        {/each}
    </ul>
</article>
