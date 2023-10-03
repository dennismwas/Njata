<script>
import logo2 from '$lib/images/logo2.png'
import imageBg from "$lib/images/banner3.jpg";
import outView from "$lib/images/06.jpg";
import bedView from "$lib/images/07.jpg";
import inView from "$lib/images/04.jpg";
import njataVid from '$lib/videos/njata.mp4'
import {onMount} from 'svelte'
import { slide } from 'svelte/transition';


let i1 = outView;

const changeImage = () => {
  let images = [outView, bedView, inView];
  const number = parseInt(Math.random() * 3);
  i1 = images[number];
};

onMount(() => {
  setInterval(changeImage, 3000);
});

function fadeSlide(node, options) {
		const slideTrans = slide(node, options)
		return {
			duration: options.duration,
			css: t => `${slideTrans.css(t)}opacity: ${t};`
		};
	}


</script>


<svelte:head>
    <title>Home • Njata Country House</title>
</svelte:head>

<main>
  <div class="relative">
    <!-- svelte-ignore a11y-missing-attribute -->
    <img class="w-full h-fit" src={imageBg} alt="njata in view" />
    <div
      class="text-center absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
    >
      <p class="font-extrabold text-2xl md:text-7xl text-white">
        <strong>Njata Country House AirBnB Nyahururu</strong>
      </p>
      <p class="font-bold md:text-2xl text-base text-center text-white pt-2">
        A peaceful, serene place for family and friends to relax and sleep.
      </p>
    </div>
  </div>

  <div class="flex flex-col md:flex-row px-12 py-8 space-y-4">
    <iframe
	title="Njata Map"
      class="h-96 w-full"
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3989.8176829390086!2d36.36763541411852!3d-0.0323868355510411!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x1829d9dfee614ccd%3A0x5e0668f7e17bb1cb!2sNjata%20Country%20House!5e0!3m2!1sen!2ske!4v1673853684658!5m2!1sen!2ske"
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
    ></iframe>

    <div class="mx-4 text-lg space-y-1">
      <h3 class="font-bold text-3xl text-blue-400">Njata Country House</h3>
      <p>
        Our unique place has tastefully spacious deluxe rooms, going an extra
        mile to give you a stay that you deserve. We are located about 5 minutes
        drive from Nyahururu town, Literally a stone throw away from Nyandarua
        National Polytechnic, along Nyahururu-Ol'Kalou road.
      </p>
      <ul class="mx-8 pt-4 space-y-2 list-disc">
        <li>A free parking spot</li>
        <li>
          The building is well secured with 24hr CCTV surveillance (day and
          night).
        </li>
        <li>Affordable accomodation rates starting from $30 per night</li>
      </ul>
    </div>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 px-12 py-8 md:space-y-24">
    <div class="mx-4 text-lg space-y-1">
      <h3 class="text-info">At Njata Country House We Offer</h3>

      <ul class="mx-8 pt-4 space-y-2 list-decimal">
        <li>Deluxe rooms</li>
        <li>Smart TVs</li>
        <li>Deluxe rooms</li>
        <li>Conference facilities</li>
        <li>Free Wifi</li>
        <li>Room Service</li>
        <li>Organized group lunches</li>
      </ul>
    </div>

    <video class="w-full h-96 p-4" poster={logo2} controls>
      <source src={njataVid} type="video/mp4" />
	  <track kind="captions" />
    </video>
  </div>

  <div class="flex flex-col md:flex-row px-12 py-8 space-y-4">
    <div>
      <div transition:fadeSlide|global="{{duration: 1000}}" >
        <!-- svelte-ignore a11y-missing-attribute -->
        <img src={i1} alt="njata preview"/>
	  </div>
    </div>
    <div class="px-4 text-lg space-y-4">
      <h4 class="my-4">In Njata Country House</h4>
      <p>
        You enjoy our close proximity to Thompson Falls and Lake Ol'bolossat,
        which is home to Hippos, Cat Fish, and a mating and hatching ground for
        the Grey Crowned Crane
      </p>
      <p>
        To make reservations contact +254702907070 or email us at: <br />
        njatacountryhouse@gmail.com or admin@njatacountryhouse.co.ke .
      </p>
    </div>
  </div>
</main>