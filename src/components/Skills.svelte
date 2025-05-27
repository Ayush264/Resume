<script>
  import { onMount } from 'svelte';
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  
  gsap.registerPlugin(ScrollTrigger);
  
  // User data
  const technicalSkills = [
    { name: "Flutter", level: 90 },
    { name: "Java", level: 85 },
    { name: "Dart", level: 85 },
    { name: "C++", level: 80 },
    { name: "DevOps", level: 75 },
    { name: "Spring Framework", level: 70 },
    { name: "Docker", level: 70 },
    { name: "Firebase", level: 85 },
    { name: "DSA", level: 80 },
    { name: "Git", level: 85 }
  ];
  
  const softSkills = [
    "Problem Solving",
    "Quick Learning",
    "Teamwork",
    "Leadership",
    "Innovation",
    "Analytics",
    "Creativity",
    "Communication"
  ];
  
  onMount(() => {
    // Animate progress bars
    ScrollTrigger.create({
      trigger: "#skills",
      start: "top 70%",
      onEnter: () => {
        gsap.to(".progress-value", {
          width: function(i, el) {
            return el.dataset.value + "%";
          },
          duration: 1.5,
          stagger: 0.1,
          ease: "power2.out"
        });
      },
      once: true
    });
  });
</script>

<section id="skills" class="section">
  <h2 class="text-3xl font-bold text-gray-800 mb-8">Skills & Expertise</h2>
  
  <div class="grid md:grid-cols-2 gap-10">
    <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-6">Technical Skills</h3>
      
      <div class="space-y-6">
        {#each technicalSkills as skill}
          <div>
            <div class="flex justify-between items-center mb-2">
              <span class="text-gray-700 font-medium">{skill.name}</span>
              <span class="text-sm text-gray-500">{skill.level}%</span>
            </div>
            
            <div class="progress-bar">
              <div 
                class="progress-value" 
                data-value={skill.level} 
                style="width: 0%;"
              ></div>
            </div>
          </div>
        {/each}
      </div>
    </div>
    
    <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-6">Professional Skills</h3>
      
      <div class="grid grid-cols-2 gap-4">
        {#each softSkills as skill}
          <div class="bg-white rounded-lg shadow-sm p-4 border border-gray-100 hover:border-primary-200 hover:shadow-md transition-all duration-300 flex items-center">
            <div class="w-2 h-2 rounded-full bg-primary-500 mr-3"></div>
            <span class="text-gray-700">{skill}</span>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>