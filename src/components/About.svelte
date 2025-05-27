<script>
  // User data
  const profileImage = "https://images.pexels.com/photos/614810/pexels-photo-614810.jpeg?auto=compress&cs=tinysrgb&w=600";
  const about = `
    Computer Science undergraduate skilled in cross-platform app development (Flutter), automation, and DevOps.
    Proficient in Java, Dart, and C++, with a strong foundation in software development, debugging, and system optimization.
    Quick learner with a problem-solving mindset, eager to grow as a Software Engineer and explore emerging technologies.
  `;
</script>

<section id="about" class="section pt-20">
  <div class="flex flex-col md:flex-row items-center md:items-start gap-8">
    
    
    <div class="flex-1">
      <h2 class="text-3xl font-bold text-gray-800 mb-6">About Me</h2>
      
      <div class="text-gray-600 leading-relaxed space-y-4">
        {#each about.split('\n').filter(paragraph => paragraph.trim()) as paragraph}
          <p>{paragraph}</p>
        {/each}
      </div>
      
      <div class="mt-8 flex flex-wrap gap-3">
        <span class="tag">Flutter</span>
        <span class="tag">Java</span>
        <span class="tag">Dart</span>
        <span class="tag">DevOps</span>
        <span class="tag">C++</span>
      </div>
    </div>
  </div>
</section>