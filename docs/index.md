---
layout: default
title: Tech Pulse
auto_title: false
---

<style>
/* Override Jekyll theme styles for section headers */
.section-header {
  background-color: #2054a6 !important;
  color: white !important;
  padding: 12px !important;
  margin: -12px -12px 12px -12px !important;
  border-radius: 5px 5px 0 0 !important;
  border-bottom: 1px solid #e1e4e8 !important;
}

.section-header * {
  color: white !important;
}

.section-header i, 
.section-header a, 
.section-header a:hover, 
.section-header a:focus, 
.section-header a:visited {
  color: white !important;
}

.cert-header {
  background-color: #2054a6 !important;
  color: white !important;
  padding: 15px !important;
}

.cert-header *, 
.cert-header i, 
.cert-header a {
  color: white !important;
}

/* Additional responsive styles */
@media (max-width: 768px) {
  .cert-header {
    padding: 12px !important;
  }
  
  .cert-header h3 {
    font-size: 16px !important;
  }
  
  .about-container {
    flex-direction: column;
  }
  
  .profile-container {
    margin-right: 0 !important;
    margin-bottom: 30px;
    width: 100% !important;
  }

  .section-header {
    font-size: 16px !important;
  }
  
  a[href^="https://kranthib.github.io"] {
    font-size: 12px !important;
  }
}

@media (max-width: 480px) {
  h1 {
    font-size: 24px !important;
  }
  .section-header {
    font-size: 15px !important;
  }
  
  [class*="fa-"] {
    font-size: 12px !important;
  }
}
</style>

<div class="about-container" style="display: flex; align-items: flex-start; margin-bottom: 30px;">
  <div class="profile-container" style="flex: 0 0 250px; margin-right: 30px;">
    <img src="https://github.com/kranthiB/tech-pulse/assets/20100300/9a736590-5588-4b5b-813c-7e25c031942e" alt="Profile Picture" style="width: 100%; border-radius: 5px;">
    <div style="margin-top: 15px;">
      <h3>Connect</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li style="margin-bottom: 8px;"><a href="https://github.com/kranthiB" style="display: flex; align-items: center; text-decoration: none; color: #0366d6;"><i class="fab fa-github" style="margin-right: 8px; font-size: 18px;"></i>GitHub</a></li>
        <li style="margin-bottom: 8px;"><a href="https://www.linkedin.com/in/kranthi-kumar-bitra/" style="display: flex; align-items: center; text-decoration: none; color: #0366d6;"><i class="fab fa-linkedin" style="margin-right: 8px; font-size: 18px;"></i>LinkedIn</a></li>
        <li><a href="https://kranthib.github.io/tech-pulse" style="display: flex; align-items: center; text-decoration: none; color: #0366d6;"><i class="fa fa-rss" style="margin-right: 8px; font-size: 18px;"></i>TechPulse</a></li>
      </ul>
    </div>
  </div>
  
  <div style="flex: 1;">
    <h1>About Me</h1>
    <p>In my role as a leader in engineering practice, I hold expertise in strategic thinking, system integrations, and design. My skills include tech stack selection, crafting solutions across multiple platforms and leveraging the latest technologies, ensuring industry security, managing migration processes, and offering thought leadership.</p>
    
    <p>I have successfully led the delivery and advancement of specialized services, showcasing proficiency in developing bespoke solutions. My capabilities extend modernization services emphasizing cloud-native characteristics and pioneering digital edge solutions encompassing IoT, IIoT, edge computing, and blockchain technologies.</p>
    
    <p>In addressing operational challenges, I have implemented solutions to detect events at the scale and respond effectively. This has proven instrumental in solving issues such as predictive maintenance, predictive quality, accurate failure diagnosis, and overall efficiency improvement.</p>
    
    <p>Additionally, I bring extensive experience in creating sustainable platforms that empower businesses to implement data-driven operations. This involves strategically placing computation and data storage close to the source of data.</p>
  </div>
</div>

<!-- Knowledge Areas section header -->
<h1 style="text-align: center; margin-bottom: 30px; color: #24292e; border-bottom: 1px solid #e1e4e8; padding-bottom: 10px;">Knowledge Areas</h1>

<!-- System Design & Platform Engineering (keep in one row) -->
<div style="display: flex; flex-wrap: wrap; gap: 15px; margin-bottom: 40px;">
  <!-- System Design Column -->
  <div style="flex: 1; min-width: 300px;">
    <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
      <h3 class="section-header">
        <i class="fa fa-sitemap" style="margin-right: 10px;"></i>System Design
      </h3>
      <p style="margin-top: 0; color: #24292e; font-size: 14px;">Architecture patterns, distributed systems, scalability, and resilience strategies.</p>
      <div style="text-align: right;">
        <a href="https://kranthib.github.io/tech-pulse/system-design.html" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Explore <i class="fa fa-arrow-right"></i></a>
      </div>
    </div>
  </div>
  
  <!-- Platform Engineering Column -->
  <div style="flex: 1; min-width: 300px;">
    <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
      <h3 class="section-header">
        <i class="fa fa-server" style="margin-right: 10px;"></i>Platform Engineering
      </h3>
      <p style="margin-top: 0; color: #24292e; font-size: 14px;">Internal developer platforms, infrastructure automation, and delivery excellence.</p>
      <div style="text-align: right;">
        <a href="https://kranthib.github.io/tech-pulse/platform-engineering.html" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Explore <i class="fa fa-arrow-right"></i></a>
      </div>
    </div>
  </div>
</div>

<!-- Data & AI (separate row) -->
<div style="margin-bottom: 40px;">
  <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
    <h3 class="section-header">
      <i class="fa fa-database" style="margin-right: 10px;"></i>Data & AI
    </h3>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; margin-top: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/data-ai/data-foundations.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-cubes" style="margin-right: 5px;"></i>Data Foundations</a>
      <a href="https://kranthib.github.io/tech-pulse/data-ai/data-engineering.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-cogs" style="margin-right: 5px;"></i>Data Engineering</a>
      <a href="https://kranthib.github.io/tech-pulse/data-ai/data-analysis.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-chart-bar" style="margin-right: 5px;"></i>Data Analysis</a>
      <a href="https://kranthib.github.io/tech-pulse/data-ai/conventional-ml.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-cog" style="margin-right: 5px;"></i>Conventional ML</a>
      <a href="https://kranthib.github.io/tech-pulse/data-ai/deep-learning.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-brain" style="margin-right: 5px;"></i>Deep Learning</a>
    </div>
  </div>
</div>

<!-- Generative AI (separate row) -->
<div style="margin-bottom: 40px;">
  <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
    <h3 class="section-header">
      <i class="fa fa-robot" style="margin-right: 10px;"></i>Generative AI
    </h3>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; margin-top: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/gen-ai/prompt-engineering.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-keyboard" style="margin-right: 5px;"></i>Prompt Engineering</a>
      <a href="https://kranthib.github.io/tech-pulse/gen-ai/llm-tier.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-layer-group" style="margin-right: 5px;"></i>LLM Tiers</a>
      <a href="https://kranthib.github.io/tech-pulse/gen-ai/rag.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-search" style="margin-right: 5px;"></i>RAG</a>
      <a href="https://kranthib.github.io/tech-pulse/gen-ai/agentic-ai.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-user-cog" style="margin-right: 5px;"></i>Agentic AI</a>
      <a href="https://kranthib.github.io/tech-pulse/gen-ai/ai-driven-software-development.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-code" style="margin-right: 5px;"></i>AI-Enabled Development</a>
    </div>
  </div>
</div>

<!-- Industrial IoT (separate row) -->
<div style="margin-bottom: 40px;">
  <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
    <h3 class="section-header">
      <i class="fa fa-industry" style="margin-right: 10px;"></i>Industrial IoT
    </h3>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; margin-top: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/industrial-iot/industrial-iot.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-industry" style="margin-right: 5px;"></i>Smart Manufacturing</a>
      <a href="https://kranthib.github.io/tech-pulse/industrial-iot/edge-gateway.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-network-wired" style="margin-right: 5px;"></i>Edge Gateway</a>
      <a href="https://kranthib.github.io/tech-pulse/industrial-iot/industry-5.0.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-rocket" style="margin-right: 5px;"></i>Industry 5.0</a>
    </div>
  </div>
</div>

<!-- Ops Mastery (separate row) -->
<div style="margin-bottom: 40px;">
  <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
    <h3 class="section-header">
      <i class="fa fa-wrench" style="margin-right: 10px;"></i>Ops Mastery
    </h3>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(110px, 1fr)); gap: 10px; margin-top: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/dev-sec-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-shield-alt" style="margin-right: 5px;"></i>DevSecOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/git-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-code-branch" style="margin-right: 5px;"></i>GitOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/fin-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-money-bill" style="margin-right: 5px;"></i>FinOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/ml-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-cogs" style="margin-right: 5px;"></i>MLOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/ai-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-robot" style="margin-right: 5px;"></i>AIOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/green-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-leaf" style="margin-right: 5px;"></i>GreenOps</a>
      <a href="https://kranthib.github.io/tech-pulse/ops-mastery/test-ops.html" style="padding: 10px; background-color: white; border-radius: 3px; text-decoration: none; color: #0366d6; text-align: center; border: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-vial" style="margin-right: 5px;"></i>TestOps</a>
    </div>
  </div>
</div>

<h1 style="text-align: center; margin-bottom: 30px; color: #24292e; border-bottom: 1px solid #e1e4e8; padding-bottom: 10px;">Frameworks & Platforms</h1>

<!-- Frameworks & Platforms section with multi-column layout -->
<div style="display: flex; flex-wrap: wrap; gap: 15px; margin-bottom: 40px;">
  <!-- Column 1 -->
  <div style="flex: 1; min-width: 300px;">
    <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
      <h3 class="section-header">
        <i class="fa fa-th-large" style="margin-right: 10px;"></i>Security & Integration
      </h3>
      <div style="display: flex; flex-direction: column; gap: 8px;">
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/enterprise-application-security-framework.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-lock" style="margin-right: 8px;"></i>Enterprise Application Security Framework</a>
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/enterprise-api-integration-and-management-platform.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-exchange-alt" style="margin-right: 8px;"></i>Enterprise API Integration and Management Platform</a>
      </div>
    </div>
  </div>
  
  <!-- Column 2 -->
  <div style="flex: 1; min-width: 300px;">
    <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
      <h3 class="section-header">
        <i class="fa fa-th-large" style="margin-right: 10px;"></i>Optimization & Performance
      </h3>
      <div style="display: flex; flex-direction: column; gap: 8px;">
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/cloud-cost-optimization-framework.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-cloud" style="margin-right: 8px;"></i>Cloud Cost Optimization Framework</a>
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/ai-code-assistant-performance-scorecard.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-chart-line" style="margin-right: 8px;"></i>AI Code Assistant Performance Scorecard</a>
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/enterprise-test-automation-platform.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-vial" style="margin-right: 8px;"></i>Enterprise Test Automation Platform</a>
      </div>
    </div>
  </div>
  
  <!-- Column 3 (New) -->
  <div style="flex: 1; min-width: 300px;">
    <div style="padding: 12px; background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16);">
      <h3 class="section-header">
        <i class="fa fa-robot" style="margin-right: 10px;"></i>Agentic AI Solutions
      </h3>
      <div style="display: flex; flex-direction: column; gap: 8px;">
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/agentic-ai-solutions/sales-meeting-preparation-agent.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-briefcase" style="margin-right: 8px;"></i>Sales Meeting Preparation Agent</a>
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/agentic-ai-solutions/wall-paint-visualizer-agent.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-briefcase" style="margin-right: 8px;"></i>Wall Paint Visualizer Agent</a>
        <a href="https://kranthib.github.io/tech-pulse/frameworks-n-platforms/agentic-ai-solutions/ai-powered-code-modernization.html" style="padding: 8px; background-color: white; border-left: 3px solid #0366d6; text-decoration: none; color: #0366d6; border-radius: 0 3px 3px 0; border-top: 1px solid #e1e4e8; border-right: 1px solid #e1e4e8; border-bottom: 1px solid #e1e4e8; font-size: 13px;"><i class="fa fa-briefcase" style="margin-right: 8px;"></i>AI-Powered Code Modernization</a>
      </div>
    </div>
  </div>
</div>

<!-- UPDATED CERTIFICATIONS SECTION -->
<h1 style="text-align: center; margin-bottom: 30px; color: #24292e; border-bottom: 1px solid #e1e4e8; padding-bottom: 10px;">Certifications</h1>

<!-- Certifications section with improved responsive layout -->
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; margin-bottom: 40px;">
  
  <!-- Databricks -->
  <div style="background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16); overflow: hidden;">
    <div class="cert-header" style="display: flex; align-items: center;">
      <i class="fa fa-database" style="margin-right: 10px; font-size: 18px;"></i>
      <h3 style="margin: 0; font-size: 18px;">Databricks</h3>
    </div>
    
    <div style="padding: 15px;">
      <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 12px;">
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/data-analyst-associate.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-chart-pie" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Data Analyst Associate</span>
        </a>
        
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/data-engineer-associate.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-database" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Data Engineer Associate</span>
        </a>
        
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/data-engineer-professional.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-cogs" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Data Engineer Professional</span>
        </a>
        
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/generative-ai-engineer-associate.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-robot" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Generative AI Engineer Associate</span>
        </a>
        
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/machine-learning-associate.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-brain" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Machine Learning Associate</span>
        </a>
        
        <a href="https://kranthib.github.io/tech-pulse/certifications/databricks/machine-learning-professional.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
          <i class="fa fa-brain" style="margin-right: 8px; color: #ff3621; font-size: 16px; flex-shrink: 0;"></i>
          <span style="font-weight: 500; font-size: 14px;">Machine Learning Professional</span>
        </a>
      </div>
    </div>
  </div>
  
  <!-- Google Cloud -->
  <div style="background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16); overflow: hidden;">
    <div class="cert-header" style="display: flex; align-items: center;">
      <i class="fa fa-cloud" style="margin-right: 10px; font-size: 18px;"></i>
      <h3 style="margin: 0; font-size: 18px;">Google Cloud</h3>
    </div>
    
    <div style="padding: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/certifications/google-cloud/professional-cloud-architect.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
        <i class="fa fa-cloud" style="margin-right: 8px; color: #4285F4; font-size: 16px; flex-shrink: 0;"></i>
        <span style="font-weight: 500; font-size: 14px;">Professional Cloud Architect</span>
      </a>
    </div>
  </div>

  <!-- Kubernetes -->
  <div style="background-color: #f6f8fa; border-radius: 5px; border: 1px solid #e1e4e8; box-shadow: 0 3px 6px rgba(0,0,0,0.16); overflow: hidden;">
    <div class="cert-header" style="display: flex; align-items: center;">
      <i class="fa fa-dharmachakra" style="margin-right: 10px; font-size: 18px;"></i>
      <h3 style="margin: 0; font-size: 18px;">Kubernetes</h3>
    </div>
    
    <div style="padding: 15px;">
      <a href="https://kranthib.github.io/tech-pulse/certifications/kubernetes/certified-kubernetes-administrator.html" style="display: flex; align-items: center; padding: 10px; background-color: white; border-radius: 4px; text-decoration: none; color: #0366d6; border: 1px solid #e1e4e8; transition: all 0.2s ease; min-height: 42px;">
        <i class="fa fa-server" style="margin-right: 8px; color: #326CE5; font-size: 16px; flex-shrink: 0;"></i>
        <span style="font-weight: 500; font-size: 14px;">Certified Kubernetes Administrator</span>
      </a>
    </div>
  </div>
</div>

<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">