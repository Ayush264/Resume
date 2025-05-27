<script>
  const currentYear = new Date().getFullYear();
  const name = "Ayush Jha";
</script>

<footer class="bg-gray-900 text-white py-12">
  <div class="container mx-auto px-4 sm:px-6 lg:px-8 max-w-5xl">
    <div class="flex flex-col md:flex-row justify-between items-center">
      <div class="mb-6 md:mb-0">
        <h2 class="text-2xl font-bold">{name}</h2>
        <p class="text-gray-400 mt-1">Software Developer</p>
      </div>
      
      <div class="text-center md:text-right">
        <p class="text-gray-400">© {currentYear} All Rights Reserved</p>
        <p class="text-sm text-gray-500 mt-1">Built with Svelte and Tailwind CSS</p>
      </div>
    </div>
    
    <div class="mt-8 pt-8 border-t border-gray-800 text-center">
      <a 
        href="#top" 
        class="inline-flex items-center text-primary-400 hover:text-primary-300 transition-colors"
      >
        <span>Back to Top</span>
        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 ml-1" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
        </svg>
      </a>
    </div>
  </div>
</footer>