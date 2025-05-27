<script>
  import { onMount } from 'svelte';
  import { gsap } from 'gsap';
  
  // User data
  const contactInfo = {
    email: "jhaayush61@gmail.com",
    phone: "+91 7838228983",
    location: "Mohali, India",
    availability: "Available for opportunities"
  };
  
  const socialLinks = [
    { name: "LinkedIn", url: "https://linkedin.com/in/ayush-jha-b688b6186", icon: "linkedin" },
    { name: "GitHub", url: "https://github.com/Ayush264", icon: "github" }
  ];
  
  let formData = {
    name: "",
    email: "",
    message: ""
  };
  
  let isSubmitting = false;
  let isSubmitted = false;
  let formElement;
  
  function handleSubmit(e) {
    e.preventDefault();
    isSubmitting = true;
    
    // Simulate form submission
    setTimeout(() => {
      isSubmitting = false;
      isSubmitted = true;
      formData = { name: "", email: "", message: "" };
      
      // Reset form after 3 seconds
      setTimeout(() => {
        isSubmitted = false;
      }, 3000);
    }, 1500);
  }
  
  onMount(() => {
    // Contact form animation
    gsap.from(formElement, { 
      opacity: 0, 
      y: 30,
      scrollTrigger: {
        trigger: formElement,
        start: "top 80%",
      },
      duration: 0.8,
      ease: "power2.out"
    });
  });
</script>

<section id="contact" class="section pb-20">
  <h2 class="text-3xl font-bold text-gray-800 mb-8">Get In Touch</h2>
  
  <div class="grid md:grid-cols-2 gap-10">
    <div>
      <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-100">
        <h3 class="text-xl font-semibold text-gray-800 mb-6">Contact Information</h3>
        
        <div class="space-y-4">
          <div class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary-500 mt-0.5 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
            <div>
              <p class="text-sm text-gray-500 mb-1">Email</p>
              <p class="text-gray-700">{contactInfo.email}</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary-500 mt-0.5 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
            <div>
              <p class="text-sm text-gray-500 mb-1">Phone</p>
              <p class="text-gray-700">{contactInfo.phone}</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary-500 mt-0.5 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
            <div>
              <p class="text-sm text-gray-500 mb-1">Location</p>
              <p class="text-gray-700">{contactInfo.location}</p>
            </div>
          </div>
          
          <div class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary-500 mt-0.5 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
            <div>
              <p class="text-sm text-gray-500 mb-1">Availability</p>
              <p class="text-gray-700">{contactInfo.availability}</p>
            </div>
          </div>
        </div>
        
        <div class="mt-8">
          <h4 class="text-lg font-semibold text-gray-800 mb-4">Connect with me</h4>
          
          <div class="flex space-x-4">
            {#each socialLinks as link}
              <a 
                href={link.url} 
                target="_blank" 
                rel="noopener noreferrer"
                class="w-10 h-10 rounded-full bg-gray-100 hover:bg-primary-100 hover:text-primary-600 flex items-center justify-center transition-colors duration-300"
                aria-label={link.name}
              >
                {#if link.icon === 'linkedin'}
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                  </svg>
                {:else if link.icon === 'github'}
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/>
                  </svg>
                {/if}
              </a>
            {/each}
          </div>
        </div>
      </div>
    </div>
    
    <div bind:this={formElement}>
      <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-100">
        <h3 class="text-xl font-semibold text-gray-800 mb-6">Send a Message</h3>
        
        {#if isSubmitted}
          <div class="bg-green-50 border border-green-200 text-green-700 rounded-lg p-4 animate-fade-in">
            <div class="flex">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              <p>Your message has been sent successfully! I'll get back to you soon.</p>
            </div>
          </div>
        {:else}
          <form on:submit={handleSubmit} class="space-y-4">
            <div>
              <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Name</label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                required
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary-500 focus:border-primary-500 transition-colors"
                placeholder="Your name"
              />
            </div>
            
            <div>
              <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                required
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary-500 focus:border-primary-500 transition-colors"
                placeholder="your.email@example.com"
              />
            </div>
            
            <div>
              <label for="message" class="block text-sm font-medium text-gray-700 mb-1">Message</label>
              <textarea
                id="message"
                bind:value={formData.message}
                required
                rows="5"
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-primary-500 focus:border-primary-500 transition-colors"
                placeholder="Your message here..."
              ></textarea>
            </div>
            
            <button
              type="submit"
              disabled={isSubmitting}
              class="w-full bg-primary-600 hover:bg-primary-700 text-white font-medium py-2.5 px-4 rounded-md transition-colors duration-300 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:ring-offset-2 disabled:opacity-70"
            >
              {#if isSubmitting}
                <span class="flex items-center justify-center">
                  <svg class="animate-spin -ml-1 mr-2 h-4 w-4 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                  Sending...
                </span>
              {:else}
                Send Message
              {/if}
            </button>
          </form>
        {/if}
      </div>
    </div>
  </div>
</section>