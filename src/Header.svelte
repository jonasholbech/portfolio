<!-- https://www.styleshout.com/demo/?theme=kards -->
<style>
    section {
        display: grid;
        place-content: center;
        text-align: center;
        height: 100vh;
    }
    .box {
        display: flex;
        flex-direction: column;
    }
    h1 {
        font-size: 74px;
        line-height: 1.071;
        margin-top: 0;
        margin-bottom: 0.6rem;

        text-shadow: 3px 3px 0px rgba(255, 255, 255, 0.2);
    }
    h2 {
        color: var(--highlight-color);
        font-size: 2.3rem;
        line-height: 1.565;
        margin-bottom: 0;
        text-transform: uppercase;
        letter-spacing: 0.3rem;
    }
    h3 {
        color: #fff;
        align-self: center;
        border: 1px solid var(--border-color);
        padding: 0 1rem;
        border-width: 0 2px;
        text-transform: uppercase;
    }
    h1,
    h2,
    h3,
    a {
        margin: 1rem;
    }
    a {
        align-self: center;
        background: transparent;
        border: 3px solid var(--border-color);
        color: white;
        padding: 0.7rem 1rem;
        font-size: 1rem;
        font-weight: bold;
        transition: all 0.5s;
        text-decoration: none;
    }
    a:after {
        display: inline-block;
        content: "ᗊ";
        font-size: 1rem;
        font-weight: normal;
        position: relative;
        left: 0.6rem;

        transition: all 0.5s;
    }

    a:hover {
        border-color: var(--highlight-color);
        cursor: pointer;
    }
    a:hover:after {
        color: var(--highlight-color);
        transform: translateY(4px);
    }
</style>

<section id="home" class="fullbleed">
    <div class="box">
        <h2>Hello</h2>
        <h1>I'm Jonas Holbech</h1>
        <h3>Front-end developer</h3>
        <a href="#aboutMe">More About Me</a>
    </div>
</section>
<!-- TODO: github, facebook, linkedin icons at bottom -->
