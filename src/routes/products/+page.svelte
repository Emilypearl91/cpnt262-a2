<script>
 import { title } from '../../lib/data'; 
  import { about } from '../../lib/data';
  import { product } from '../../lib/data';
  import { home } from '../../lib/data';
  
  // today's special cards
 let products = [
  {id: 1,
    title: 'Corn Lettuce Bowl',
    description: 'This bowl is made with corn, lettuce, tomato and fish',
    URL: '/images/amy-syiek-4irgyik6Q3U-unsplash.jpg',
    price: 12,
  quantity: 1},
  {
    id: 2,
  title: 'Shrimp Tomato Bowl',
  description: 'This shrimp feta tomato bowl is made lettuce, tomato, croutons, parmesan, feta, pacific white shrimp and topped with our signature dressing made in house.',
  URL: '/images/ryan-concepcion-w_z0RJCSBiE-unsplash.jpg',
  price: 12,
  quantity: 1
  },
  {id: 3,
    title: 'Edamame Salmon Bowl',
    description: 'This edamame salmon bowl is made lettuce, corn, cucumber, tomato, cabbage, green onion, salmon and hard boiled eggs.',
    URL: '/images/anh-nguyen-kcA-c3f_3FE-unsplash.jpg',
    price: 12,
  quantity: 1},
    {id: 4,
      title: 'Sesame Shrimp Bowl',
      info: 'This sesame shrimp bowl is made with seaweed, mushrooms, parsley, shrimp, rice noodles and tomatoes',
      URL: '/images/food-photographer-FtpgFeUQuAY-unsplash.jpg',
      price: 12,
    quantity: 1},
    { id: 5,
      title: ' Radish Green Bowl',
      info: 'This radish green salad bowl is made with radishes, cucumber, onions, leafy green mix and pita bread.',
      URL: '/images/sina-piryae-bBzjWthTqb8-unsplash.jpg',
      price: 12,
    quantity: 1},
    {id: 6,
      title: 'Chicken Rice Bowl',
      info: 'This chicken rice bowl is made with corn, rice, tomatoes and grilled chicken.',
      URL: '/images/food-photographer-zhkhwGrqilw-unsplash.jpg',
      price: 12,
    quantity: 1}
];

 
let cart = [];

 const addToCart = (product) => {
		for(let item of cart) {
				if(item.id === products.id) {
					products.quantity += 1
					cart = cart;
					return;
				}
		}
		cart = [...cart, product]
	}
  const minusItem = (product) => {
		for(let item of cart) {
				if(item.id === product.id) {
					if(product.quantity > 1 ) {
							product.quantity -= 1
							cart = cart
					} else {
							cart = cart.filter((cartItem) => cartItem != product)
					}
					return;
				}
		}
	}
	
	const plusItem = (product) => {
		for(let item of cart) {
			if(item.id === product.id) {
				item.quantity += 1
				cart = cart;
				return;
			}
		}
	}

	$: total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0)
	
  // show shopping cart when navbar icon is clicked
  function showCart() {
  const x =  cartList;
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
</script>
<section class="relative">
<section class="flex flex-row justify-end h-16 bg-surface-600 ">
  <!---shop name--->
    <h1 class="h1 mr-60">{title}</h1>
    
  <!---navbar--->
  <section>
  <button type="button" class="btn variant-ghost-primary m-2 h-10 "><a href="{home.URL}">{home.title}</a></button>
  <button type="button" class="btn variant-ghost-primary m-2 h-10"><a href="{product.URL}">{product.title}</a></button>
  <button type="button" class="btn variant-ghost-primary  m-2 h-10"><a href="{about.URL}">{about.title}</a></button>
  <!---shopping cart button --->
  <button on:click={() => showCart()} type="button" class="btn-icon variant-ghost-primary m-2"><svg xmlns="http://www.w3.org/2000/svg" height="14" width="15.75" viewBox="0 0 576 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.--><path fill="#ffffff" d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96z"/></svg>
    </button>
    <div class=" text-base text-center text-white bg-red-800 absolute top-0 right-0 w-[20px] rounded m-1">{cart.length}</div>
  
</section>
</section>
<!-- Shopping Cart -->
  <div id="cartList" class=" w-[600px] h-[400px] p-2 bg-primary-500 float float-right absolute top-15 right-0">
	{#each cart as item }
		{#if item.quantity > 0}
		<div class="cart-item grid grid-cols-3">
			<img width="50" src={item.URL} alt={item.title}/>
			<div>{item.quantity}
				<button on:click={() => plusItem(item)}>+</button>
				<button on:click={() => minusItem(item)}>-</button>
			</div>
			<p>${item.price * item.quantity}</p>
		</div> 
		{/if}
	{/each}
	<div class="total text-right">
		<h4>Total: $ {total}</h4>
	</div>
</div>
</section>
<body class="content">
  <section class="flex flex-row flex-wrap justify-around m-4 p-2">
{#each products as product}

  <div class="card p-4 max-w-xs variant-ghost-primary m-4">
    <img src="{product.URL}" alt="corn,lettuce,tomato and meat salad bowl ">
    <h3 class="h3">{product.title}</h3>
    <p>{product.description}</p>
    <p class="text-lg font-bold">${product.price}</p>
    <button type="button" class="btn variant-filled-surface m-2" on:click={() => addToCart(product)}>Add to Cart</button>
  </div>
{/each}
</section>
</body>