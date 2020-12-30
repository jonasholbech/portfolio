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
        align-self: center;
    }
    .inner {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
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
        color: var(--highlight-color);
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
        background: rgba(255, 255, 255, 0.2);
        position: absolute;
        left: 0;
        bottom: 0;
    }
    .mention time:after {
        display: none;
    }
    .timeline {
        display: grid;
        grid-template-columns: 60px 1fr;
        column-gap: 1rem;
    }
    .content {
        border-top: 1px solid rgba(204, 204, 204, 0.1);
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
        color: black;
        background: white;
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

<section id="resume" class="fullbleed">
    <div class="inner">
        <h1>Resume</h1>
        <p>So, what have I done so far?</p>
        <article id="work">
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
        <div>
            <article id="education">
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
                            <p>
                                <time>{education.start} - {education.end}</time>
                            </p>
                            <h3>{education.level}</h3>
                            <p>{education.notes}</p>
                        </div>
                    {/each}
                </div>
            </article>

            <article id="mentions">
                <h1>Honorable Mentions</h1>
                <div class="timeline">
                    <div class="icon"><span>?</span></div>
                    <div class="content mention">
                        <h2>???</h2>
                        <p><time>Present - ???</time></p>
                    </div>
                    {#each mentions as mention, index (index)}
                        <div class="icon">
                            <MentionIcon />
                        </div>
                        <div class="content mention">
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
    </div>
</section>
