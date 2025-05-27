<script>
  // User data
  const experiences = [
    {
      title: "Growth Hacker",
      company: "MemeChat Pvt Ltd",
      period: "March 2021 - Sept 2024",
      description: "Worked as a Growth Hacker at MemeChat Pvt Ltd in a hybrid work environment, focusing on user engagement and analytics.",
      achievements: [
        "Utilized analytical skills for growth management",
        "Managed user notifications and engagement strategies",
        "Worked with CleverTap and Firebase for analytics",
        "Implemented data-driven growth strategies"
      ]
    }
  ];
</script>

<section id="experience" class="section">
  <h2 class="text-3xl font-bold text-gray-800 mb-8">Professional Experience</h2>
  
  <div class="space-y-12">
    {#each experiences as job, i}
      <div class="relative pl-8 md:pl-0">
        <!-- Timeline dot and line for desktop -->
        <div class="hidden md:block absolute left-0 top-0 bottom-0 w-px bg-gray-200 ml-6">
          <div class="absolute top-1.5 -ml-1.5 w-3 h-3 rounded-full bg-primary-500 border-2 border-white"></div>
        </div>
        
        <!-- Timeline dot for mobile -->
        <div class="md:hidden absolute left-0 top-1.5 w-3 h-3 rounded-full bg-primary-500 border-2 border-white"></div>
        
        <div class="md:ml-16">
          <div class="flex flex-col md:flex-row md:items-center justify-between mb-2">
            <h3 class="text-xl font-semibold text-gray-800">{job.title}</h3>
            <span class="text-sm text-gray-500 mt-1 md:mt-0">{job.period}</span>
          </div>
          
          <p class="text-primary-600 font-medium mb-3">{job.company}</p>
          
          <p class="text-gray-600 mb-4">{job.description}</p>
          
          <div class="pl-4 border-l-2 border-primary-200 space-y-2">
            {#each job.achievements as achievement}
              <p class="text-gray-700">• {achievement}</p>
            {/each}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>