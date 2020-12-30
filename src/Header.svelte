<script>
</script>

<!-- https://www.styleshout.com/demo/?theme=kards -->
<style>
    /*
        
        background: #457fca; 
        background: -webkit-linear-gradient(
            to left,
            #5691c8,
            #457fca
        );
        background: linear-gradient(
            to left,
            #5691c8,
            #457fca
        );
        */
    section {
        grid-column: 1/-1;
        text-align: center;
        height: 100vh;
        display: grid;
        place-content: center;
        background: #000000;
        background: -webkit-linear-gradient(
            to bottom,
            #000000,
            #434343
        ); /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to bottom, #000000, #434343);
    }
    .box {
        display: flex;
        flex-direction: column;
    }
    h1 {
        color: #ffffff;
        font-size: 74px;
        line-height: 1.071;

        margin-top: 0;
        margin-bottom: 0.6rem;
        margin-left: auto;
        margin-right: auto;
        text-shadow: 3px 3px 0px rgba(255, 255, 255, 0.2);
    }
    h2 {
        color: var(--red);
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
        color: var(--border-color);
        transition: all 0.5s;
    }

    a:hover {
        border-color: var(--red);
        cursor: pointer;
    }
    a:hover:after {
        color: var(--red);
        transform: translateY(4px);
    }
</style>

<section id="home">
    <div class="box">
        <h2>Hello World</h2>
        <h1>I'm Jonas Holbech</h1>
        <h3>Front-end developer</h3>
        <a href="#aboutMe">More About Me</a>
    </div>
</section>
<!-- TODO: github, facebook, linkedin icons at bottom -->
