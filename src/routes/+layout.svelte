<script>
	import Footer from './Footer.svelte';
import Header from './Header.svelte';
import './styles.css';


let data=     [   { name: "description", content: "Njata Country House AirBnB located in Nyahururu Olkalou Road" },
        {
            name:"keywords",
      content:"mile, stone, nyahururu-olkalou, along, polytechnic, national, nyandarua, airbnb,house,country house,nyandarua county,nyanadarua national polytechnic,airbnb house,house for airbnb,airbnb near me,airbnb nakuru,airbnb login,meaning of airbnb,airbnb nairobi,airbnb mombasa,airbnb meaning,country airbnb,airbnb country,airbnb country house, njata, bed and breakfast,bed,breakfast,hotel,njata counmtry house,secure parking,nyanadarua,nyahururu,nyandarua polytechnic,ol'kalou,rooms,guest,deluze rooms,spacious rooms,cctv surveillance,njata country house"
        },
        { name: "url", content: "https://njatacountryhouse.co.ke" },
        {
            name: "MobileOptimized", content: "width"
        },
        { name: "HandheldFriendly", content: "true" },
		
        { name:'language' , content:'EN'},
        { name: "robots", content: "index,follow" },
        { name:"viewport" ,content:"width=device-width, initial-scale=1.0"},


        { name: "twitter:title", content: "Njata Country House AirBnB" },
        { name: "twitter:description", content: "Njata Country House AirBnB" }
	]
</script>


<svelte:head>
	<title>Njata Country House</title>
	{#each data as dt }
	<meta name={dt.name} content={dt.content} />
	{/each}
</svelte:head>

<div class="app">
	<Header />

	<main>
		<slot />
	</main>

	<Footer />

</div>
