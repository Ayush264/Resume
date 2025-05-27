<script>
  // User data
  const education = [
    {
      degree: "BE - Computer Science Engineering",
      school: "Chandigarh University",
      year: "2022 - 2026 (Expected)",
      description: "Currently pursuing Computer Science Engineering with a CGPA of 7.21/10"
    },
    {
      degree: "12th Grade (Non-medical)",
      school: "Rajkiya Pratibha Vikas Vidyalaya",
      year: "2022",
      description: "Completed senior secondary education with 81% marks"
    },
    {
      degree: "10th Grade",
      school: "Rajkiya Pratibha Vikas Vidyalaya",
      year: "2020",
      description: "Completed secondary education with 84% marks"
    }
  ];
  
  const certifications = [
    {
      name: "Developing Industrial Internet of Things",
      issuer: "University of Colorado Boulder",
      year: "2024"
    },
    {
      name: "Django for Everybody Specialization",
      issuer: "University of Michigan",
      year: "2024"
    },
    {
      name: "Blockchain Technology using Ethereum and Polygon",
      issuer: "Metacrafters",
      year: "2024"
    },
    {
      name: "React Native",
      issuer: "Meta",
      year: "2024"
    }
  ];
</script>

<section id="education" class="section">
  <h2 class="text-3xl font-bold text-gray-800 mb-8">Education & Certifications</h2>
  
  <div class="grid md:grid-cols-2 gap-8">
    <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-6">Academic Education</h3>
      
      <div class="space-y-8">
        {#each education as edu}
          <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-100 hover:shadow-md transition-shadow duration-300">
            <div class="flex justify-between items-start mb-2">
              <h4 class="text-lg font-semibold text-gray-800">{edu.degree}</h4>
              <span class="text-sm text-gray-500">{edu.year}</span>
            </div>
            
            <p class="text-primary-600 font-medium mb-3">{edu.school}</p>
            
            <p class="text-gray-600">{edu.description}</p>
          </div>
        {/each}
      </div>
    </div>
    
    <div>
      <h3 class="text-xl font-semibold text-gray-800 mb-6">Professional Certifications</h3>
      
      <div class="space-y-4">
        {#each certifications as cert}
          <div class="bg-white rounded-lg shadow-sm p-5 border border-gray-100 hover:shadow-md transition-shadow duration-300">
            <div class="flex justify-between items-center mb-1">
              <h4 class="text-md font-semibold text-gray-800">{cert.name}</h4>
              <span class="text-sm text-gray-500">{cert.year}</span>
            </div>
            
            <p class="text-primary-600 text-sm">{cert.issuer}</p>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>