---
title: "Supercharge Your APS Development with Agent Skills"
url: "https://aps.autodesk.com/blog/supercharge-your-aps-development-agent-skills"
date: "Thu, 30 Apr 2026 14:05:07 +0000"
author: "petr.broz@autodesk.com"
feed_url: "https://aps.autodesk.com/rss.xml"
---
<span class="field field--name-title field--type-string field--label-hidden">Supercharge Your APS Development with Agent Skills</span>
<span class="field field--name-uid field--type-entity-reference field--label-hidden"><span>petr.broz@auto…</span></span>

<div class="node__date">
  <p class="dhig-typography-eyebrow dhig-mt-0">30 Apr 2026</p>
</div>

      <div class="field field--name-field-author field--type-entity-reference field--label-hidden field__items">
              <div class="field__item">

<article class="node node__author view-mode__list">
  <div class="node__content">
    
            <div class="field field--name-field-primary-image field--type-image field--label-hidden field__item">  <img alt="alt" class="image-style-author" height="200" src="https://aps.autodesk.com/sites/default/files/styles/author/public/2025-06/IMG_0873.JPG?itok=KR9ZNOs2" width="200" />


</div>
      
    <a href="https://aps.autodesk.com/author/petr-broz">Petr Broz</a>
  </div>
</article>
</div>
          </div>
  <div class="block-share">
  <p>Share</p>
  <div class="a2a_kit a2a_kit_size_30 addtoany_list"><a class="a2a_button_linkedin"></a><a class="a2a_button_facebook"></a><a class="a2a_button_twitter"></a></div></div>

            <div class="field field--name-field-primary-image field--type-image field--label-hidden field__item">  <img alt="alt" height="819" src="https://aps.autodesk.com/sites/default/files/2026-04/aps-skills.png" width="1456" />

</div>
      
            <div class="clearfix text-formatted field field--name-field-body field--type-text-with-summary field--label-hidden field__item"><p></p>
<p dir="auto">Building on top of&nbsp;<a href="https://aps.autodesk.com/">Autodesk Platform Services</a>&nbsp;means navigating a rich but wide API surface. Getting any of it right the first time takes familiarity that developers new to APS rarely have on day one.</p>
<p dir="auto">That's why the Autodesk Developer Advocacy team is launching a new open-source repository:&nbsp;<strong><a href="https://github.com/autodesk-platform-services/skills">https://github.com/autodesk-platform-services/skills</a></strong>, a growing collection of agent skills purpose-built for anyone who wants to build on top of our platform.</p>
<h2 dir="auto" id="what-are-agent-skills">What are agent skills?</h2>
<p dir="auto">Agent skills are self-contained instruction sets (typically a collection of Markdown files) that teach an AI coding agent how to perform a specific, well-defined task. Think of them as portable domain expertise: instead of you re-explaining how APS authentication works every single time you start a new conversation, a skill carries that knowledge and guides the agent through the right steps automatically. Skills are composable, version-controllable, and shareable across a team. You can learn more about the format and best practices at&nbsp;<a href="https://agentskills.io/">agentskills.io</a>.</p>
<p dir="auto">Skills are supported by a growing number of AI coding agents.&nbsp;<a href="https://claude.ai/code">Claude Code</a>&nbsp;has first-class support for them, and the broader ecosystem is converging on the same convention. You can also install and manage skills across agents using the&nbsp;<a href="https://www.npmjs.com/package/skills"><code>skills</code></a>&nbsp;CLI utility. Once a skill is installed, the agent can load and apply it automatically when your prompt calls for it, or you can trigger a skill explicitly using a command (e.g.,&nbsp;<code>/aps-mcp-server-gen</code>).</p>
<h2 dir="auto" id="available-skills">Available skills</h2>
<p dir="auto">The collection is just getting started, but here's what's in it today:</p>
<h3 dir="auto" id="aps-mcp-server-gen-scaffold-a-custom-mcp-server-for-aps"><a href="https://github.com/autodesk-platform-services/skills/tree/main/skills/aps-mcp-server-gen"><code>aps-mcp-server-gen</code></a>: Scaffold a custom MCP server for APS</h3>
<p dir="auto">The&nbsp;<a href="https://modelcontextprotocol.io/">Model Context Protocol (MCP)</a>&nbsp;is an open standard for connecting AI agents to external tools and data sources. This skill generates a fully working MCP server that integrates with APS in your choice of:</p>
<ul dir="auto">
<li dir="auto"><strong>Language</strong>: Node.js/TypeScript, .NET/C#, or Python</li>
<li dir="auto"><strong>Transport</strong>: STDIO (for local clients like Claude Desktop) or Streamable HTTP (for cloud deployment)</li>
<li dir="auto"><strong>Authentication</strong>: 2-legged OAuth, Secure Service Accounts, or 3-legged OAuth</li>
</ul>
<p dir="auto">The skill doesn't produce a skeleton with TODOs. It generates complete, runnable code with auth setup, MCP tools, a test suite with mocked APS calls, and a README that walks you through connecting to an MCP client.</p>
<h2 dir="auto" id="how-to-install-skills">How to install skills</h2>
<p dir="auto">You can install skills globally (available in every project) or per-project.</p>
<h3 dir="auto" id="using-the-skills-utility-recommended">Using the&nbsp;<code>skills</code>&nbsp;utility (recommended)</h3>
<ul dir="auto">
<li dir="auto">Make sure you have&nbsp;<a href="https://nodejs.org/en">Node.js</a>&nbsp;installed, and the <a href="https://docs.npmjs.com/cli/v11/commands/npx">npx</a> utility available in Bash or PowerShell</li>
<li dir="auto">Use the <a href="https://www.npmjs.com/package/skills">skills</a> CLI&nbsp;to manage skills, for example:</li>
</ul>
<pre>
<code class="language-bash" dir="auto"># Install all APS skills globally
npx skills add --global autodesk-platform-services/skills

# ... or ...

# Install a single skill into the current project only
npx skills add --project autodesk-platform-services/skills --skill aps-mcp-server-gen
</code></pre><h3 dir="auto" id="manual-installation-on-macos">Manual installation on macOS</h3>
<pre>
<code class="language-bash" dir="auto"># Clone the skills repo
git clone https://github.com/autodesk-platform-services/skills.git aps-skills
# Install the&nbsp;aps-mcp-server-gen&nbsp;skill globally for Claude Code
cp -r aps-skills/skills/aps-mcp-server-gen ~/.claude/skills/
</code></pre><h3 dir="auto" id="manual-installation-on-windows">Manual installation on Windows</h3>
<pre>
<code class="language-powershell" dir="auto"># Clone the skills repo
git clone https://github.com/autodesk-platform-services/skills.git aps-skills
# Install the&nbsp;aps-mcp-server-gen&nbsp;skill globally for Claude Code
Copy-Item -Recurse aps-skills\skills\aps-mcp-server-gen "$env:USERPROFILE\.claude\skills\"
</code></pre><h3 dir="auto" id="verify-the-installation">Verify the installation</h3>
<p dir="auto">Once installed, simply describe what you want in your AI agent, something like&nbsp;<em>"create an APS MCP server in Python"</em>, and the agent will automatically load the relevant skill and guide you through the rest.</p>
<h2 dir="auto" id="see-it-in-action">See it in action</h2>
<p dir="auto">The video below shows a full walkthrough of installing the&nbsp;<a href="https://github.com/autodesk-platform-services/skills/tree/main/skills/aps-mcp-server-gen"><code>aps-mcp-server-gen</code></a>&nbsp;skill and using it to scaffold a new MCP server from scratch in Claude Code:</p>
<p dir="auto">&nbsp;</p>
<div class="video-embed-field-provider-youtube video-embed-field-responsive-video">
</div>

</div>
      
      <div class="field field--name-field-categories field--type-entity-reference field--label-hidden field__items">
              <div class="field__item"><a href="https://aps.autodesk.com/topics/tips-and-tricks" hreflang="en">Tips and Tricks</a></div>
              <div class="field__item"><a href="https://aps.autodesk.com/topics/ai" hreflang="en">AI</a></div>
          </div>
