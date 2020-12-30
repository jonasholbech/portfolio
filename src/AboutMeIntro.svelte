<div class="intro">
        <h1>About</h1>
        <h2>Let me introduce myself</h2>
        <img src="jholcolor.jpg" alt="">
        <blockquote>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti eius excepturi mollitia unde cum quam magni vel assumenda delectus soluta commodi optio recusandae, inventore reprehenderit praesentium facilis! Placeat, dolor quaerat?
            Optio modi natus maiores odit, inventore ea nobis eveniet assumenda facere consequatur sapiente ducimus qui nihil illum amet illo ratione. A quia illum ipsa asperiores perferendis dolorum ea doloremque omnis!
        </blockquote>
    </div>

    <style>
    .intro {
        display:grid;
        grid-template-columns:1fr;
        justify-self: center;
        
        
    }
    .intro>h1, .intro>h2{
        grid-column: 1/-1;
        text-align: center;
        margin: 0 auto;
    }
    .intro>h1 {
        color:var(--red);
    }
    .intro>h2 {
        margin-bottom:1rem;
    }
    .intro>blockquote {
        max-width: 60ch;
    }
    img {
        border-radius:50%;
        width:150px;
        justify-self: center;
        align-self: start;
        margin-top:1.4rem;
    }
     @media (min-width: 600px) {
		.intro {
            grid-template-columns: 150px 1fr;	
        }
        
	}
    </style>