<script>
import { title } from '../../data'; 
import { about } from '../../data';
import { product } from '../../data';
import { home } from '../../data';

</script>

<section class="flex flex-row justify-end h-16 bg-surface-600 ">
<!---shop name--->
  <h1 class="h1 mr-60">{title}</h1>
  
<!---navbar links--->
<section>
<button type="button" class="btn variant-ghost-primary m-2 h-10 "><a href="{home.URL}">{home.title}</a></button>
<button type="button" class="btn variant-ghost-primary m-2 h-10"><a href="{product.URL}">{product.title}</a></button>
<button type="button" class="btn variant-ghost-primary  m-2 h-10"><a href="{about.URL}">{about.title}</a></button>

</section>

 
</section>
