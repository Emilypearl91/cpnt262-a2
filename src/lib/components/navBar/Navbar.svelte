<script>
import { AppBar } from '@skeletonlabs/skeleton';
import { Avatar } from '@skeletonlabs/skeleton';

import { title } from '../../data'; 
import { initials } from '../../data';
import { about } from '../../data';
import { product } from '../../data';
import { home } from '../../data';

</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
  <svelte:fragment slot="lead">
<!---profile icon--->
    <Avatar initials="{initials}" background="bg-primary-500" />
  </svelte:fragment>
<!---shop name--->
  <h1 class="h1">{title}</h1>
  <svelte:fragment slot="trail">
<!---navbar links--->
<button type="button" class="btn variant-ghost-primary"><a href="{home.URL}">{home.title}</a></button>
<button type="button" class="btn variant-ghost-primary"><a href="{product.URL}">{product.title}</a></button>
<button type="button" class="btn variant-ghost-primary"><a href="{about.URL}">{about.title}</a></button>
          </svelte:fragment>
</AppBar>

 
