<script>
  import { onMount } from 'svelte';
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  
  import Header from './components/Header.svelte';
  import About from './components/About.svelte';
  import Experience from './components/Experience.svelte';
  import Education from './components/Education.svelte';
  import Skills from './components/Skills.svelte';
  import Contact from './components/Contact.svelte';
  import Footer from './components/Footer.svelte';
  
  gsap.registerPlugin(ScrollTrigger);
  
  onMount(() => {
    // Animate each section
    gsap.utils.toArray('.section').forEach((section, i) => {
      gsap.set(section, { 
        opacity: 0, 
        y: 20 
      });
      
      ScrollTrigger.create({
        trigger: section,
        start: "top 80%",
        end: "bottom 20%",
        onEnter: () => {
          gsap.to(section, { 
            opacity: 1, 
            y: 0, 
            duration: 0.8, 
            ease: "power2.out",
            delay: i * 0.1
          });
        },
        once: true
      });
    });
  });
</script>

<main class="min-h-screen">
  <Header />
  
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 max-w-5xl">
    <About />
    <Experience />
    <Education />
    <Skills />
    <Contact />
  </div>
  
  <Footer />
</main>