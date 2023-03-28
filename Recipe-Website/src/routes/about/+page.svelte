<nav class="navbar">
  <a href="/">Home</a>
  <a href="/recipe">R.O.T.D.</a>
  <a href="/contact">Contact</a>
  <a href="/about">About Us</a> 
</nav>

<main>
  <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
  </head>
  <body>
    <div class="Title">
      <h1>ABOUT US</h1>
    </div>
    <div class="Info">
      <div id="Story" class="Story">
        <h2>WHO WE ARE</h2>
        <p><em>Welcome to our food recipe website, where we are passionate about bringing you the best recipes from around the world. 
              We are a team of food enthusiasts who love to cook and share our favorite recipes with others. Our goal is to create a one-stop-shop for food lovers looking to explore new flavors and cuisines. 
              Our recipe collection is constantly growing, and we are always on the lookout for delicious and unique dishes to add to our site. 
              We hope that our recipes inspire you to try new things in the kitchen and help you create memorable meals for yourself, your family, and your friends.</em>
        </p>
      </div>
      <div id="Space" class="Space">
        
      </div>
      <div id="Mission" class="Mission">
        <h2>OUR MISSION</h2>
        <p><em>Food recipes are more than just instructions for making a meal; they are a way to connect with our cultural heritage, share our love of cooking with others, and express our creativity in the kitchen. 
              Each recipe tells a story, revealing the unique flavors, techniques, and ingredients of a particular time and place. 
              So when we cook and share recipes, we are not just feeding our bodies, but also nourishing our souls and celebrating the richness and diversity of our world."</em>
        </p>
      </div>
    </div>
    
    <div id="Other_Plateform" class="Git">
      <!-- svelte-ignore security-anchor-rel-noreferrer -->
      <!-- svelte-ignore a11y-missing-content -->
      <a href="https://github.com/Elliot-Massey1/Website_Creation" target="_blank" class="fa fa-github"></a>
    </div>
  </body>
</main>

<style>
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

  main { 
    background: url("about_us.jpeg") 50% 50% no-repeat;
    background-repeat: no-repeat;
    background-size: cover;
    padding-bottom: 60px;
  }

  body{
    margin:0;
    color:black;
    text-align: center;

  }

  h1 {
    margin-top: 0px;
    padding-top: 20px;
    font-size:60px;
    font-family:Gill Sans;
  }
  
  .Info h2 {
    font-size:25px;
  }

  .Story {
    vertical-align:top;
    display: inline-block;
    width: max(319px, 24.3vw);
  }

  .Space {
    display: inline-block;
    margin-left: max(92px, 10.8vw);
    width: max(308px, 24.3vw);
  }

  .Mission {
    vertical-align:top;
    display: inline-block;
    width: max(319px, 24.3vw);
  }

  #Other_Plateform {
    margin-top: 110px;
    text-align: center;
    font-size:40px;
  }

  div {
    font-family:Arial,sans-serif;
  }

  .Git a {
    color: black;
    padding-top: 1vw;
  }

  a:hover {
    color: yellow;
  }

</style>