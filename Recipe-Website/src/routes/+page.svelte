<script>

  export let recipes = [
    {
      title : 'Cheeseburger', 
      link: '/cheeseburger',
      image: 'Burger.jpg',
      description: "What do you call a burger that's cooler than cool? An 'iceburger'! But this burger is more than just a clever pun - it's stacked high with juicy beef, crispy bacon, melted cheese, and all the fixings. You'll take a bite and think, 'this burger is so good, it's almost criminal! So go ahead, take a bite out of crime and sink your teeth into this delicious burger."
      },
    {
      title: 'Butter chicken',
      link: '/butter_chicken',
      image: 'Butter chicken.jpg',
      description: 'Why did the chicken cross the road? To get to the creamy, buttery goodness of this mouth-watering butter chicken dish! With tender chicken simmered in a fragrant blend of spices and a rich, creamy sauce, this recipe will have you clucking with delight. So why wait? Get ready to cross the road and whip up this finger-licking good butter chicken!'
    },
    {
      title: 'Chicken wings',
      link: '/chicken_wings',
      image: 'Chicken wings.jpg',
      description: "Why did the chicken go to the seance? To talk to the other side...of the sauce, that is! These crispy chicken wings are so flavorful, they'll have you communicating with the other side of your taste buds. Whether you like your wings hot and spicy or sweet and tangy, this recipe is sure to satisfy. So why wait? Get your chicken wings on and let your taste buds do the talking!"
    }
  ];

</script>


<main>
  <nav class="navbar">
    <a href="/">Home</a>
    <a href="/recipe">R.O.T.D.</a>
    <a href="/contact">Contact</a>
    <a href="/about">About Us</a>
  </nav>
  
  <div class="top">
    <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">
      <img class="logo" src="Essec logo.jpeg.jpg" alt="Logo">
    </a>
    <h1>ESSEC RECIPES</h1>
  </div>
  
  <div class="hero">
    <div class="hero-image">        
      <img src="main.jpg" alt="Food" >
      <h1 class="hero-title">Group 10's favorite recipes</h1>
    </div>
  </div>

  <div class="search-bar">
      <form>
        <label for="search">Search recipes:</label>
        <input type="text" id="search" name="search" placeholder="Don't Forget to Refresh the Page to see the dropdown list again!">        
        <button type="submit">Search</button>
      </form>   
    </div>
    <ul class="dropdown">
      <li><a href="/recipe1">New Potato Lentil Salad</a></li>
      <li><a href="/recipe2">Honey Lime Chicken</a></li>
      <li><a href="/recipe3">Brioche Chocolate Rolls</a></li>
    </ul>   

    
    <script>
      const searchInput = document.getElementById("search");
      const dropdown = document.querySelector(".dropdown");

      searchInput.addEventListener("click", function() {
        dropdown.style.display = "block";
      });

      dropdown.querySelectorAll("a").forEach(function(link) {
        link.addEventListener("click", function() {
          dropdown.style.display = "none";
        });
      });

      document.addEventListener("click", function(event) {
        if (!dropdown.contains(event.target) && event.target !== searchInput) {
          dropdown.style.display = "none";
        }
        else {
          dropdown.style.display = "block";
        }
      });
    </script>

<style>
  .dropdown {
    display: none;
    background-color: #D3D3D3;
    z-index: 1;
    margin-top: 0;
    padding: 0;
    font-family: 'Montserrat', sans-serif;
    justify-content: center;
    align-items: center;
    margin: auto; 
    width: max(58.3%, 300px);
        
  }

  .dropdown li {
    list-style-type: none;
    margin: 0;
    padding: 5px;
  }

  .dropdown li a {
    display: block;
    text-decoration: none;
    color: black;
  }

  .dropdown li a:hover {
    background-color: #f5f5f5;
    display: block;
  }

  .search-bar {
    display: flex;
    justify-content: center;
    border: 1px solid #ccc;
    background-color: #a3a1a1;
    text-align: center;
    padding: 20px;
    width: max(58.3%, 300px);
    margin: auto; 
  }

  .search-bar form {
    display: flex;
    font-family: 'Montserrat', sans-serif;
    justify-content: center;
    align-items: center;
  }

  .search-bar label {
    margin-right: 15px;
    font-size: 16px;
  }

  .search-bar input[type="text"] {
    border: none;
    border-right: 1px solid #ccc;
    font-size: 16px;
    width: 38vw; 
    height: 40px; 
    padding: 5px 10px;
  }

  .search-bar input[type="text"]:focus {
    outline: none;
  }

  .search-bar button[type="submit"] {
    height: 50px; 
    padding: 5px 15px;
    background-color: black; 
    color: white;
    border: none;
    border-radius: 0px 5px 5px 0px;
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    cursor: pointer;
  }

  .search-bar button[type="submit"]:hover {
    background-color: #444; 
  }
</style>


  <div class="recipes">
    {#each recipes as recipe}
      <div class="recipe">
        <img src={recipe.image} alt={recipe.title}>
        <h2  class="recipe-title" ><a href= {recipe.link}>{recipe.title}</a></h2>
        <p class="recipe-description">{recipe.description}</p>
      </div>
    {/each}
  </div>
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

  .top{
    display: flex;
    justify-content: center;
    padding-top: 20px;
  }

  .top h1 {
    font-family: 'Montserrat', sans-serif;
    font-size: max(3.1vw, 33px);
    text-align: center;
    margin-top: 2rem;
    margin-bottom: 2.5rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: #333;
    text-shadow: 2px 2px 2px #ccc;
  }

  .logo {
    width: 100px;
    height: 100px;
    transition: all 0.3s ease;
    padding-top: 10px;
    padding-right: max(40px, 10vw);
    padding-left: max(40px, 0vw);
  }

  .logo:hover {
    filter: brightness(10);
  }

  .logo:active {
    filter: brightness(0.8);
  }

  .hero {
    display: flex;
    justify-content: center;
    background-color: #f5f5f5;
    border: 1px solid black;
    box-shadow: 0px 0px 10px gray;
    text-align: center;
    padding: min(50px, 7vw) min(65px, 12.5vw);
    width: 53.3%;
    margin: min(20px, 1.5vw) auto; 
  }

  .hero-image {
    position: relative;
    display: inline-block;
    border: 1px solid black; 
    box-shadow: 0px 0px 10px gray; 
    padding: 10px; 
  }

  .hero-image img {
    width: 100%;
    height: auto;
    display: block;
  }

  .hero-title {
    font-family: 'Montserrat', sans-serif;
    font-size: max(2.35vw, 13px);
    text-align: center;
    position: absolute;
    top: min(185px, 16vw);
    left: 50%;
    transform: translate(-50%, -50%);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: black;
    text-shadow: 2px 2px 2px #ccc;
  }

  

  .recipes {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    padding-bottom: 10px;
    
  }

  .recipe {
    flex-basis: calc(33.33% - 20px);
    margin-bottom: 30px;
    border: 1px solid #ddd;
    padding: 20px;
    box-sizing: border-box;
    min-width: 390px;
    min-height: 500;
    font-family: 'Montserrat', sans-serif;
  }

  .recipe img {
    width: max(16px, 100%);
    height: auto;
    display: block;
    margin-bottom: 10px;
  }

  .recipe-title {
    display: flex;   
    justify-content: center;   
    font-size: 24px;
    margin: 0;
  }

  .recipes .recipe .recipe-title:hover {
    color:#291377;   
  }

  .recipe-description {
    font-size: 16px;
    margin: 10px 0;}
</style>