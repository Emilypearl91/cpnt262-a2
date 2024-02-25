<script> 
import { cornLettuce } from "../../data";
import { shrimpBowl } from "../../data";
import { edamameSalmon } from "../../data";
import { bestsellers } from "../../data";

</script>

<h2 class="h2 text-center m-4">Todays specials</h2>
<section class="flex flex-row justify-around m-8">

  <div class="card p-4 max-w-xs variant-ghost-primary">
    <img src="{cornLettuce.URL}" alt="corn,lettuce,tomato and meat salad bowl ">
    <h3 class="h3">{cornLettuce.title}</h3>
    <p>{cornLettuce.description}</p>

  </div>

  <div class="card p-4 max-w-xs variant-ghost-primary">
    <img src="{edamameSalmon.URL}" alt=" salad bowl with lettuce, corn, cucumber, tomato, cabbage, green onion, salmon and hard boiled eggs.">
    <h3 class="h3">{edamameSalmon.title}</h3>
    <p>{edamameSalmon.description}</p>
  </div>

  <div class="card p-4 max-w-xs variant-ghost-primary">
    <img src="{shrimpBowl.URL}" alt="salad with lettuce, tomato, croutons, parmesan, feta, shrimp">
    <h3 class="h3">{shrimpBowl.title}</h3>
    <p>{shrimpBowl.description}</p>
  </div>
</section>

<h2 class="h2 text-center m-4">Bestsellers</h2>
<section class="flex flex-row justify-around m-8">
<div class="card p-4 max-w-xs variant-ghost-primary">
<img src="{bestsellers.sesameURL}" alt=" rice noodle bowl seaweed, mushrooms, parsley, shrimp and tomatoes">
  <h3 class="h3">{bestsellers.sesameTitle}</h3>
<p>{bestsellers.sesameInfo}</p>
</div>
<div class="card p-4 max-w-xs variant-ghost-primary">
  <img src="{bestsellers.radishURL}" alt="salad bowl with radishes, cucumber, onions, leafy green mix and pita bread">
  <h3 class="h3">{bestsellers.radishTitle}</h3>
<p>{bestsellers.radishInfo}</p>
</div>
<div class="card p-4 max-w-xs variant-ghost-primary">
  <img src="{bestsellers.chickenURL}" alt="chicken rice bowl with corn, rice, tomatoes and grilled chicken.">
  <h3 class="h3">{bestsellers.chickenTitle}</h3>
<p>{bestsellers.chickenInfo}</p>
</div>
</section>