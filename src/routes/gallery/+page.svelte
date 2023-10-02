<script>
import i1 from '$lib/images/01.jpg'
import i2 from '$lib/images/02.jpg'
import i3 from '$lib/images/03.jpg'
import i6 from '$lib/images/06.jpg'
import i15 from '$lib/images/15.jpg'
import i7 from '$lib/images/07.jpg'
import i8 from '$lib/images/08.jpg'
import i17 from '$lib/images/17.jpg'
import i11 from '$lib/images/11.jpg'
import i13 from '$lib/images/13.jpg'
import i14 from '$lib/images/14.jpg'


const images = [i1, i2, i3, i14, i11, i15, i17, i6, i7, i8, i13];

const generateAlt = (str) => `image ${str}`;

</script>

<svelte:head>
    <title>Gallery • Njata Country House</title>
</svelte:head>


<div class="grid grid-cols-1 md:grid-cols-3">
    {#each images as image , index}
     <img class="px-5 py-5" alt={generateAlt(index)} src={image}>
    {/each}
</div>