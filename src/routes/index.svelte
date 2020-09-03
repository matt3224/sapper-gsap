<section id="section1">
   <span id="line1"></span>
</section>

<a href="/about">Click to change page</a>

<script>
   import { onMount, onDestroy } from 'svelte';
   import { gsap } from 'gsap';
   import { ScrollTrigger } from 'gsap/ScrollTrigger';

   onMount(() => {
      gsap.registerPlugin(ScrollTrigger);

      gsap.from("#line1", {
         scrollTrigger: {
            trigger: "#section1",
            scrub: true,
            start: "top top",
            end: "bottom top"
         },
         scaleX: 0,
         transformOrigin: "left center", 
         ease: "none"
      });
   });

   onDestroy(() => ScrollTrigger.refresh())
</script>

<style>
   section {
      min-height: 300vh;
   }

   a {
      left: 0; top: 0;
      position: fixed;
   }

   span {
      width: 100%;
      max-width: 800px;
      height: 8px;
      margin: 4rem;
      position: fixed;
      display: inline-block;
      background-color: black;
   }
</style>