<script>
  import { onMount } from 'svelte';
  import { gsap } from 'gsap';
  
  // User data
  const name = "Ayush Jha";
  const title = "Software Developer";
  
  let navLinks = [
    { name: "About", href: "#about" },
    { name: "Experience", href: "#experience" },
    { name: "Education", href: "#education" },
    { name: "Skills", href: "#skills" },
    { name: "Contact", href: "#contact" }
  ];
  
  let isMenuOpen = false;
  let headerElement;
  let isScrolled = false;
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
  
  function handleScroll() {
    isScrolled = window.scrollY > 50;
  }
  
  onMount(() => {
    window.addEventListener('scroll', handleScroll);
    
    // Header animation
    gsap.from(headerElement, { 
      y: -100, 
      opacity: 0, 
      duration: 0.8, 
      ease: "power3.out" 
    });
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<header 
  bind:this={headerElement}
  class={`fixed top-0 left-0 right-0 z-50 transition-all duration-300 py-4 ${isScrolled ? 'bg-white/95 backdrop-blur-sm shadow-sm' : 'bg-transparent'}`}
>
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 max-w-5xl">
    <div class="flex justify-between items-center">
      <div>
        <h1 class="text-xl md:text-2xl font-bold text-primary-700">{name}</h1>
        <p class="text-sm text-gray-600">{title}</p>
      </div>
      
      <!-- Desktop menu -->
      <nav class="hidden md:block">
        <ul class="flex space-x-8">
          {#each navLinks as link}
            <li>
              <a 
                href={link.href} 
                class="text-gray-600 hover:text-primary-600 transition-colors duration-300"
              >
                {link.name}
              </a>
            </li>
          {/each}
        </ul>
      </nav>
      
      <!-- Mobile menu button -->
      <button 
        class="md:hidden p-2 text-gray-600 hover:text-primary-600 focus:outline-none" 
        on:click={toggleMenu}
        aria-label={isMenuOpen ? 'Close menu' : 'Open menu'}
      >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="w-6 h-6">
          {#if isMenuOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          {/if}
        </svg>
      </button>
    </div>
    
    <!-- Mobile menu -->
    {#if isMenuOpen}
      <nav class="md:hidden mt-4 py-3 bg-white rounded-lg shadow-lg animate-fade-in">
        <ul class="space-y-3">
          {#each navLinks as link}
            <li>
              <a 
                href={link.href} 
                class="block px-4 py-2 text-gray-700 hover:bg-primary-50 hover:text-primary-600"
                on:click={() => { isMenuOpen = false; }}
              >
                {link.name}
              </a>
            </li>
          {/each}
        </ul>
      </nav>
    {/if}
  </div>
</header>

<div class="h-24"></div> <!-- Spacer for fixed header -->