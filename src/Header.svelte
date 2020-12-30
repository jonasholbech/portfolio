<script></script>

<section id="home">
    <div class="box">
        <h2>Hello World</h2>
        <h1>I'm Jonas Holbech</h1>
        <h3>Front-end developer</h3>
        <a href="#aboutMe">More About Me</a>
    </div>
</section>
<!-- TODO: github, facebook, linkedin icons at bottom -->
<!-- https://www.styleshout.com/demo/?theme=kards -->
<style>

section {
    grid-column:1/-1;
    background-color:black;
    text-align:center;
    height:100vh;
    display:grid;
    place-content: center;
}
.box {
    display:flex;
    flex-direction: column;
}
h1 {
    color: #FFFFFF;
    font-size: 84px;
    line-height: 1.071;
    max-width: 900px;
    margin-top: 0;
    margin-bottom: .6rem;
    margin-left: auto;
    margin-right: auto;
    text-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
}
h2 {
    color:var(--red);
    font-size: 2.3rem;
    line-height: 1.565;
    margin-bottom: 0;
    text-transform: uppercase;
    letter-spacing: .3rem;
}
h3 {
    color:#fff; 
    align-self: center;
    border: 1px solid var(--border-color);
    padding:0 1rem;
    border-width: 0 2px;
    text-transform: uppercase; 
    
}
h1,h2,h3,a {
    margin:1rem;
}
a {
    align-self: center;
    background:transparent;
    border: 3px solid var(--border-color);
    color:white;
    padding:0.7rem 1rem;
    font-size:1rem;
    font-weight:bold;
    transition:all 0.5s;
    text-decoration: none;
}
a:after {
    display: inline-block;
    content: "ᗊ";
    font-size: 1.0rem;
    font-weight: normal;
    position: relative;
    left: .6rem;
    color:var(--border-color);
    transition: all 0.5s;
}

a:hover {
    border-color:var(--red);
    cursor:pointer;
}
a:hover:after {
    color: var(--red);
    transform:translateY(4px);
}
</style>