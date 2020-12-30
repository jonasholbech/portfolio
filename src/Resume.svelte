<script>
    import BookIcon from "./icons/BookIcon.svelte";
    import MentionIcon from "./icons/MentionIcon.svelte";
    import WorkIcon from "./icons/WorkIcon.svelte";
    import workPlaces from "./data/work";
    import educations from "./data/educations";
    import mentions from "./data/mentions";
</script>

<style>
    section {
        background-color: #ebebeb;
        align-self: center;
    }
    .inner {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(500px, 1fr));
        column-gap: 2rem;
    }
    .inner > h1,
    .inner > p {
        grid-column: 1/-1;
    }
    article {
        margin-right: 1rem;
    }
    h1 {
        color: var(--red);
        text-align: center;
    }
    h2 {
        font-size: 1rem;
        font-weight: bold;
    }
    h3 {
        font-size: 0.8rem;
        padding-top: 1rem;
    }
    p {
        font-size: 0.7rem;
    }
    h1 + p {
        text-align: center;
    }
    time {
        position: relative;
        padding-bottom: 1rem;
    }
    time:after {
        content: "";
        display: block;
        height: 3px;
        width: 50px;
        background: rgba(0, 0, 0, 0.2);
        position: absolute;
        left: 0;
        bottom: 0;
    }
    .timeline {
        display: grid;
        grid-template-columns: 60px 1fr;
        column-gap: 1rem;
    }
    .content {
        border-top: 1px solid #ccc;
        padding: 1rem;
    }

    .content h2 {
        margin-top: 0;
        padding-top: 0;
        line-height: 1;
    }
    .icon img,
    .icon span {
        display: block;
        max-width: 100%;
        height: auto;
        border-radius: 50%;
        transform: translateX(30px);
    }
    .icon span {
        text-align: center;
        font-size: 2rem;
        color: white;
        background: black;
        height: 60px;
    }
    .icon svg {
        /*empty ruleset, moved to global, svelte strips this one out*/
    }
    .icon {
        border-right: 2px solid #ccc;
        transform: translateX(-30px);
    }
</style>

<section class="fullbleed" id="resume">
    <div class="inner">
        <h1>Resume</h1>
        <p>So, what have I done so far?</p>
        <article>
            <h1>Work Experience</h1>
            <div class="timeline">
                <div class="icon"><span>?</span></div>
                <div class="content">
                    <h2>???</h2>
                    <p><time>Present - ???</time></p>
                </div>
                {#each workPlaces as place, index (index)}
                    <div class="icon">
                        <WorkIcon />
                    </div>
                    <div class="content">
                        <h2>{place.title}, {place.education}</h2>
                        <p><time>{place.start} - {place.end}</time></p>
                        <h3>{place.workplaceShort} - {place.workplaceFull}</h3>
                        <p>{place.description}</p>
                    </div>
                {/each}
            </div>
        </article>

        <article>
            <h1>Education</h1>
            <div class="timeline">
                <div class="icon"><span>?</span></div>
                <div class="content">
                    <h2>???</h2>
                    <p><time>Present - ???</time></p>
                </div>
                {#each educations as education, index (index)}
                    <div class="icon">
                        <BookIcon />
                    </div>
                    <div class="content">
                        <h2>{education.name}</h2>
                        <p><time>{education.start} - {education.end}</time></p>
                        <h3>{education.level}</h3>
                        <p>{education.notes}</p>
                    </div>
                {/each}
            </div>
        </article>

        <article>
            <h1>Honorable Mentions</h1>
            <div class="timeline">
                <div class="icon"><span>?</span></div>
                <div class="content">
                    <h2>???</h2>
                    <p><time>Present - ???</time></p>
                </div>
                {#each mentions as mention, index (index)}
                    <div class="icon">
                        <MentionIcon />
                    </div>
                    <div class="content">
                        <h2>{mention.what}</h2>
                        <p>
                            <time>{mention.date}</time>
                            -
                            {@html mention.notes}
                        </p>
                    </div>
                {/each}
            </div>
        </article>
    </div>
</section>
