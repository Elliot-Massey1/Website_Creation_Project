<script>

    //import { crossfade } from "svelte/types/runtime/transition";
    let crossed = false;
    function crossline(){
        alert("Clicked");
        crossed = !crossed;
    }


</script>
<body>
    <nav class="navbar">
        <a href="/">Home</a>
        <a href="/recipe">R.O.T.D.</a>
        <a href="/contact">Contact</a>
        <a href="/about">About Us</a>
    </nav>
    <header>
        <h1>Cheeseburger</h1>
        <div class="subtitle-text">
            <p><strong>Servings:</strong> 1</p>
            <p><strong>Prep Time:</strong> 20 minutes</p>
            <p><strong>Difficulty:</strong> Medium</p>
        </div>
        <div class="subtitle-img">
            <img class="intro-img" src="ser_2.jpg" alt="Pic Serving">
            <img class="intro-img" src="prep_2.jpg" alt="Pic Preping">
            <img class="intro-img" src="dif_2.jpg" alt="Pic Difficulty">
        </div>
    </header>
    <hr>
    <main>
        <div class="container_1">
            <img class="recipe-image" src="Burger.jpg" alt="Food img">
        </div>
        <div class="container_2">
            <div class="ingredients">
                <h2 class="ingredients-title">Basic Ingredients</h2>
                <ul id="ingredients-list">
                    <li><input type="checkbox" class="ingredient-checkbox"  ><span class="ingredient-text">Soft Hamburger Bun</span></li>
                    <li><input type="checkbox" class="ingredient-checkbox"><span class="ingredient-text">Freshly Ground Beef</span></li>
                    <li><input type="checkbox" class="ingredient-checkbox"><span class="ingredient-text">Cheese</span></li>
                    <li><input type="checkbox" class="ingredient-checkbox"><span class="ingredient-text">Tomato</span></li>
                    <li><input type="checkbox" class="ingredient-checkbox"><span class="ingredient-text">Lettuce</span></li>
                    <li><input type="checkbox" class="ingredient-checkbox"><span class="ingredient-text">Salt and pepper to taste</span></li>
                </ul>
            </div>
            <div class="steps">
                <h2 class="steps-title">Steps</h2>
                <a href="https://www.seriouseats.com/ultra-smashed-cheeseburger-recipe-food-lab">
                    <p>If you like this recipe, check it out in this link!</p>
                </a>
            </div>
        </div>

    </main>
</body>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Cabin+Condensed&family=Lobster&family=Oregano:ital@1&display=swap');

    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0px;
        background-color: white;
    }
    
    .navbar {
        display: flex;
        justify-content: center;
        background-color: rgb(126, 122, 122);
        color: #fff;
        font-family: 'Montserrat', sans-serif;
        font-size: 1.2rem;
        border-bottom: 1px solid #ccc;
        width: 370px; 
        margin: 0 auto; 
    }

    .navbar a {
        color: #fff;
        text-decoration: none;
        padding: 12px;        
        border-right: 1px solid #ccc;
        align-items: center;
    }

    .navbar a:hover {
        background-color: #444; 
    }

    .navbar a:last-child {
        border-right: none;
    }

    /* Title/Heading */
    h1 {
        background-color: #249540d0;
        font-family: lobster;
        font-size: 50px;
        color: #fffffff1;
        text-align: center;
        padding-top: 10px;
        padding-bottom: 15px;
        margin: 0;
    }
    .subtitle-text {
        display: flex;
        justify-content: space-evenly;
        text-align: center;
        background-color: white;
        font-size: 13px;
    }
    .subtitle-img{
        display: flex;
        justify-content: space-evenly;
        text-align: center;
    }
    .intro-img {
        display: flex;        
        justify-content: space-between;
        padding-top: -20px;
        background-color: white;

        height: 10vh;
        width: 10vw;
        max-width: 50px;
        max-height: 50px;

        vertical-align: top;
        display: inline-block;
        /*
        width: 50px;
        height: 50px; 
        */
    }
    

    main {
        background-image: url("https://images.pexels.com/photos/616401/pexels-photo-616401.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
        background-size: cover;
        width: 100%;
        height: 100%;
        padding-bottom: 20px;
    }

    /* Img food */
    .container_1 {
        width: 100%;
        height: auto;
        display: block;
        display: flex;
        justify-content: space-between;
        margin: -8px;

    }
    .recipe-image {
        display:block; 
        margin:auto; 
        text-align:center;
        padding-top: 20px;
        height: 30vh;
        width: 60vw;
        max-width: 350px;
    }


    /* 2 Columns Ingr-Steps*/
    .container_2 {
        display: flex;
        justify-content: space-between;
        margin: 30px;
    }

    /*Column Ingr*/
    .ingredients {
        background-image: url("note_3.jpg");
        padding: 0px;
        border-radius: 5px;
        width: 45%;
        border: 1px solid #181818ce;
        background-color: white;
    }
    /*Header Ingr*/
    .ingredients h2 {
        background-color: #040F0f;
        color: #fff;
        font-size: 24px;
        font-family: lobster;
        text-align: center;
        padding: 10px;
        margin: 0 0 10px;
        border: 1px solid #1c1c1cc3;
        border-radius: 4px;
    }
    .ingredients li {
        display: flex;
        text-align: center;
        
        font-family: cabin;
        font-size: 20px;
        list-style-type: none;
        margin-left: -25px;
        margin-bottom: 3px;
    }

    .ingredients li:before {
        content: "";
        display: inline-block;
        position: absolute;
        left: 10px;
        top: 50%;
        transform: translateY(-50%);
        width: 20px;
        height: 20px;
    }

    .ingredients input[type="checkbox"] {
        display: flexbox;
    }    

    /*Column Steps*/
    .steps {
        background-image: url("note_w.jpg");
        padding: 0px;
        border-radius: 5px;
        width: 50%;
        border: 1px solid #181818ce;
    }
    /*Header Steps*/
    .steps h2 {
        background-color: #0E3013;
        color: #fff;
        font-family: lobster;
        font-size: 24px;
        font-weight: bold;
        text-align: center;
        padding: 10px;
        margin: 0 0 10px;
        border-radius: 5px;
    }
    .steps p {
        font-family: cabin;
        font-size: 20px;
        font-weight: bold;
        text-align: center;
    }
</style>