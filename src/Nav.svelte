<script>
    let open = null;
    $: svgOpen = open === true ? "open" : open === false ? "closed" : null;
    let scrolled = window.pageYOffset > 30;
    window.addEventListener("scroll", (e) => {
        if (window.pageYOffset > 30) {
            scrolled = true;
        } else {
            scrolled = false;
        }
    });
</script>

<style>
    header {
        position: fixed;
        background: #272727;
        width: 100vw;
        display: flex;
        justify-content: space-between;
        align-content: center;
        height: 50px;
        z-index: 100;
    }
    h1 {
        color: white;
        margin-right: 1rem;
    }
    button {
        margin-left: 1rem;
    }
    nav div {
        position: absolute;
        top: 50px;
        left: 0;
        display: flex;
        flex-direction: column;
        background: black;
        padding: 0 2rem 0rem 2rem;
        overflow: hidden;
        transition: 1s height;
    }
    /* TODO: style links*/

    .indented {
        margin-left: 1rem;
    }
    div.closed {
        height: 0;
    }
    div.open {
        height: 12rem;
    }
    svg {
        width: 50px;
        height: 50px;
    }
    rect {
        fill: var(--highlight-color);
    }
    svg rect {
        transition: 1s all;
        transform-origin: 50% 50%;
    }
    svg rect:first-child {
        transform: translateY(-20px);
    }
    svg rect:last-child {
        transform: translateY(20px);
    }
    svg.open rect:first-child {
        animation: 1s topbarOpen forwards;
    }
    svg.closed rect:first-child {
        animation: 1s topbarClose forwards;
    }
    svg.open rect:last-child {
        animation: 1s bottombarOpen forwards;
    }
    svg.closed rect:last-child {
        animation: 1s bottombarClose forwards;
    }
    svg rect:nth-child(2) {
        transition: 0.5s 0.5s all;
    }
    svg.open rect:nth-child(2) {
        opacity: 0;
    }
    svg.closed rect:nth-child(2) {
        opacity: 1;
    }

    @keyframes topbarOpen {
        0% {
            transform: translateY(-20px);
        }
        50% {
            transform: translateY(0px);
        }
        100% {
            transform: translateY(0px) rotate(-45deg);
        }
    }
    @keyframes topbarClose {
        100% {
            transform: translateY(-20px);
        }
        50% {
            transform: translateY(0px);
        }
        0% {
            transform: translateY(0px) rotate(-45deg);
        }
    }
    @keyframes bottombarOpen {
        0% {
            transform: translateY(20px);
        }
        50% {
            transform: translateY(0px);
        }
        100% {
            transform: translateY(0px) rotate(45deg);
        }
    }
    @keyframes bottombarClose {
        100% {
            transform: translateY(20px);
        }
        50% {
            transform: translateY(0px);
        }
        0% {
            transform: translateY(0px) rotate(45deg);
        }
    }
    a {
        color: white;
        text-decoration: none;
        font-weight: bold;
    }
    button {
        all: unset;
    }
    .scrolled {
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
    }
</style>

<header class:scrolled>
    <nav>
        <button on:click={() => (open = !open)}>
            <svg viewBox="0 0 100 86" class={svgOpen}>
                <rect x="20" y="40" width="60" height="6" />
                <rect x="20" y="40" width="60" height="6" />
                <rect x="20" y="40" width="60" height="6" />
            </svg>
        </button>
        <div class={open ? 'open' : 'closed'}>
            <a on:click={() => (open = !open)} href="#home">Home</a>
            <a on:click={() => (open = !open)} href="#aboutMe">About</a>
            <a on:click={() => (open = !open)} href="#resume">Resume</a>
            <a class="indented" href="#work">Work Experience</a>
            <a class="indented" href="#education">Education</a>
            <a class="indented" href="#mentions">Honorable Mentions</a>
        </div>
    </nav>

    <h1>Jonas Holbech</h1>
</header>
