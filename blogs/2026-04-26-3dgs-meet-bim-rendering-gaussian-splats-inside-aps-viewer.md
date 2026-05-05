---
title: "3DGS meet BIM: Rendering Gaussian Splats inside APS Viewer"
url: "https://aps.autodesk.com/blog/3dgs-meet-bim-rendering-gaussian-splats-inside-aps-viewer"
date: "Sun, 26 Apr 2026 20:07:19 +0000"
author: "bealem"
feed_url: "https://aps.autodesk.com/rss.xml"
---
<span class="field field--name-title field--type-string field--label-hidden">3DGS meet BIM: Rendering Gaussian Splats inside APS Viewer</span>
<span class="field field--name-uid field--type-entity-reference field--label-hidden"><span>bealem</span></span>

<div class="node__date">
  <p class="dhig-typography-eyebrow dhig-mt-0">26 Apr 2026</p>
</div>

      <div class="field field--name-field-author field--type-entity-reference field--label-hidden field__items">
              <div class="field__item">

<article class="node node__author view-mode__list">
  <div class="node__content">
    
            <div class="field field--name-field-primary-image field--type-image field--label-hidden field__item">  <img alt="alt" class="image-style-author" height="200" src="https://aps.autodesk.com/sites/default/files/styles/author/public/2025-09/1758661744.png?itok=LVsaFlix" width="200" />


</div>
      
    <a href="https://aps.autodesk.com/author/michael-beale">Michael  Beale</a>
  </div>
</article>
</div>
          </div>
  <div class="block-share">
  <p>Share</p>
  <div class="a2a_kit a2a_kit_size_30 addtoany_list"><a class="a2a_button_linkedin"></a><a class="a2a_button_facebook"></a><a class="a2a_button_twitter"></a></div></div>

            <div class="field field--name-field-primary-image field--type-image field--label-hidden field__item">  <img alt="alt" height="974" src="https://aps.autodesk.com/sites/default/files/2026-04/SCR-20260425-qvuh_0.jpeg" width="1456" />

</div>
      
            <div class="clearfix text-formatted field field--name-field-body field--type-text-with-summary field--label-hidden field__item"><p>What if you could overlay a photorealistic reality capture directly onto your BIM model — right in the browser, with no plugins, no server-side rendering, and no separate viewport?</p>
<p class="lead">Now, with 3DGS and APS Viewer, you can. &nbsp;With the recent announcement of WorldLabs and XGRIDS new PortalCam, it was time to update the&nbsp;<a href="https://aps.autodesk.com/blog/devcon-amsterdam-ssa-workshops-x-grids-gaussian-splats-meetup">DevCon2025 code</a><br />
&nbsp;</p>
<h2 class="lead"><strong>Try it Live:</strong> <a href="https://wallabyway.github.io/gaussian-splats-lmv/">wallabyway / Gaussian-splats-lmv</a></h2>
<p>
<video controls="controls" poster="https://wallabyway.github.io/gaussian-splats-lmv/blog/lmv-3dgs-hq1-half.webp" src="https://wallabyway.github.io/gaussian-splats-lmv/blog/lmv-3dgs-hq1.mp4" width="770">&nbsp;</video>
</p>
<p>This demo decodes LCC, then renders 3D Gaussian Splats on top of a Revit model - all inside the web based APS Viewer.<br />
The entire thing is roughly 600 lines of JavaScript.</p>
<hr />
<h2>Quick Start</h2>
<p>Download the source code (<strong><a href="https://github.com/wallabyway/gaussian-splats-lmv">wallabyway/gaussian-splats-lmv</a>)</strong> and serve the files with any static HTTP server:</p>
<pre>
<code># Python
python3 -m http.server 8000

# Node (npx)
npx serve .
</code></pre><p>Then open <code>http://localhost:8000</code> in a modern browser&nbsp;or load a custom LCC model like this:</p>
<pre>
<code>http://localhost:8000/?lcc=https://d2pqszqfxcodwz.cloudfront.net/lcc-model/showroom+level+2/showroom2.lcc
</code></pre><p>Try loading other Sample LCC scenes (see references)&nbsp;</p>
<hr />
<h2>Five Technical Highlights</h2>
<p>Click the link for full technical details:</p>
<h3>1. <a href="https://github.com/wallabyway/gaussian-splats-lmv/blob/main/blog/topic3.md">From Point Clouds to Gaussian Splats: The Shader</a></h3>
<p>If you’ve ever rendered a point cloud (<a href="https://aps.autodesk.com/blog/combining-pointclouds-and-revit-models-forgeviewer">previously</a>), you’re halfway there. The leap from fixed-size dots to oriented Gaussian ellipses is smaller than it looks — each splat is just an instanced quad whose “texture” is a mathematically computed Gaussian falloff, shaped by projecting a 3D covariance matrix through the camera.</p>
<figure><img alt="Point cloud vs Gaussian splat" src="https://wallabyway.github.io/gaussian-splats-lmv/blog/diagrams/topic3-points-vs-splats.webp" />
<figcaption>
<p>Point cloud vs Gaussian splat</p>
<p>&nbsp;</p>
</figcaption>
</figure>
<h3>2. <a href="https://github.com/wallabyway/gaussian-splats-lmv/blob/main/blog/topic1.md">The LCC Format and the XGRIDS LiDAR Pipeline</a></h3>
<p>How a single Gaussian splat gets packed into 32 bytes of binary data — and why a LiDAR scanner on your phone can skip the most expensive step in the traditional 3DGS pipeline. XGRIDS uses hardware depth sensing instead of COLMAP’s hours-long photogrammetry reconstruction, making splat capture viable on a handheld device.</p>
<figure><img alt="32-byte Gaussian splat record binary layout" src="https://wallabyway.github.io/gaussian-splats-lmv/blog/diagrams/topic1-byte-layout.webp" />
<figcaption>32-byte splat record layout (LCC <code>data.bin</code>)</figcaption>
</figure>
<figure><img alt="XGRIDS LiDAR vs COLMAP pipeline" src="https://wallabyway.github.io/gaussian-splats-lmv/blog/diagrams/topic1-pipeline-comparison.webp" />
<figcaption>XGRIDS LiDAR vs COLMAP pipeline</figcaption>
</figure>
<h3>&nbsp;</h3>
<h3>3. <a href="https://github.com/wallabyway/gaussian-splats-lmv/blob/main/blog/topic2.md">Why Splats Need Sorting</a></h3>
<p>Transparent primitives can’t hide behind a Z-buffer. Every camera movement means re-sorting millions of splats back-to-front (without using OIT techniques or ray-tracing).</p>
<figure><img src="https://wallabyway.github.io/gaussian-splats-lmv/blog/diagrams/topic2-sort-order.webp" />
<figcaption>Why the Sort Order matters for Transparency</figcaption>
</figure>
<p>A 65536-bucket counting sort runs in O(n) time inside a dedicated Web Worker, keeping the main thread free for rendering.</p>
<figure><img alt="Counting sort and Web Worker architecture" src="https://wallabyway.github.io/gaussian-splats-lmv/blog/diagrams/topic2-sort-worker.webp" />
<figcaption>Counting sort and Web Worker architecture</figcaption>
</figure>
<h3>&nbsp;</h3>
<figure>
<figcaption>&nbsp;</figcaption>
</figure>
<h3>4. <a href="https://github.com/wallabyway/gaussian-splats-lmv/blob/main/blog/topic4.md">Section Planes: Making Splats Play Nice with BIM Tools</a></h3>
<p>The BIM viewer’s section tool cuts through both the Revit model and the splat overlay at exactly the same plane. The vertex shader evaluates the same half-space equation that LMV uses internally, so the cut aligns perfectly with no coordinate transforms or sign flips.</p>
<h3>&nbsp;</h3>
<hr />
<h2>Add 3DGS to Your Own APS Viewer</h2>
<p>Already have an APS Viewer app? You can drop Gaussian splats into it with four steps.</p>
<p><strong>1. Import the loader and renderer</strong></p>
<pre>
<code>import { LCCLoader } from './lcc-loader.mjs';
import { GaussianSplatRenderer } from './splat-renderer.mjs';
</code></pre><p><strong>2. Load the LCC file and initialize the renderer</strong></p>
<pre>
<code>const loader = new LCCLoader({ targetLOD: 4 });
const data = await loader.load('https://your-cdn.com/path/to/model.lcc');

const splatRenderer = new GaussianSplatRenderer();
await splatRenderer.init(data);

// Scale and rotate to align with your model
const METERS_TO_FEET = 3.28084;
splatRenderer.mesh.scale.set(METERS_TO_FEET, METERS_TO_FEET, METERS_TO_FEET);
</code></pre><p><strong>3. Add the splat mesh as an overlay</strong></p>
<pre>
<code>viewer.impl.createOverlayScene('splats');
viewer.impl.addOverlay('splats', splatRenderer.mesh);
</code></pre><p><strong>4. Drive the render loop on camera changes</strong></p>
<pre>
<code>viewer.addEventListener(Autodesk.Viewing.CAMERA_CHANGE_EVENT, () =&gt; {
    splatRenderer.update(viewer.impl.camera);
    viewer.impl.invalidate(false, false, true);
});
</code></pre><p>That’s it. The splats will sort, render, and composite automatically. If you also want section plane support, add one more listener:</p>
<pre>
<code>viewer.addEventListener(Autodesk.Viewing.CUTPLANES_CHANGE_EVENT, () =&gt; {
    splatRenderer.setCutPlanes(viewer.getCutPlanes() || []);
    viewer.impl.invalidate(false, false, true);
});
</code></pre><hr />
<h2>The Result</h2>
<p>Realistic looking 3D Gaussian Splats (XGRIDS LCC) composited on top of a Revit model inside the APS Viewer, in the browser. Pan, orbit, and section the BIM model; the splat overlay respects the same camera, the same section planes, and the same compositing stack as the native geometry. The entire implementation is roughly 600 lines of JavaScript across three modules.</p>
<p><strong>Try it live:</strong>&nbsp;<a href="https://wallabyway.github.io/gaussian-splats-lmv/">wallabyway.github.io/gaussian-splats-lmv</a>.</p>
<hr />
<h2>Source</h2>
<p>The complete source code for this demo is in the repository <a href="https://github.com/wallabyway/gaussian-splats-lmv"><strong>wallabyway/gaussian-splats-lmv</strong></a>. &nbsp;The implementation lives in three files:</p>
<table>
<thead>
<tr>
<th>File</th>
<th>Lines</th>
<th>Role</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>lcc-loader.mjs</code></td>
<td>~210</td>
<td>Decodes the XGRIDS LCC binary format (see part 1 below for the spec details)</td>
</tr>
<tr>
<td><code>splat-renderer.mjs</code></td>
<td>~375</td>
<td>vertex/fragment shaders, Web Worker depth sort, cut-plane support</td>
</tr>
<tr>
<td><code>app.mjs</code></td>
<td>~115</td>
<td>Viewer init, Revit model loading, splat overlay</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<hr />
<h2>References</h2>
<ul>
<li><strong>XGRIDS Sample Scans</strong> — see here: <a href="https://developer.xgrids.com/#/download?page=sampledata">developer portal — Sample data</a>.</li>
<li><strong>lcc-decoder</strong> — <a href="https://github.com/wallabyway/lcc-decoder">github.com/wallabyway/lcc-decoder</a> — reference decoder / Three.js viewer this demo was ported from.</li>
<li><strong>antimatter15/splat</strong> — <a href="https://github.com/antimatter15/splat">github.com/antimatter15/splat</a> — early WebGL 3DGS viewer; influenced common shader conventions in the ecosystem.</li>
<li><strong>LCC whitepaper</strong> — <a href="https://github.com/xgrids/LCCWhitepaper">github.com/xgrids/LCCWhitepaper</a></li>
</ul>
<hr />
<p class="footer-sig"><em>Made with <a href="https://github.com/wallabyway/agile-ai-methodology"><strong>Blueprint</strong></a>.</em></p>
<p class="footer-sig">Follow on <a href="https://x.com/micbeale">X @micbeale</a> · <a href="https://www.linkedin.com/in/mibeale/">Connect on LinkedIn</a></p>
</div>
      
      <div class="field field--name-field-categories field--type-entity-reference field--label-hidden field__items">
              <div class="field__item"><a href="https://aps.autodesk.com/topics/ai" hreflang="en">AI</a></div>
              <div class="field__item"><a href="https://aps.autodesk.com/apis-and-services/viewer" hreflang="en">Viewer</a></div>
              <div class="field__item"><a href="https://aps.autodesk.com/autodesk-products/reality-capture" hreflang="en">Reality Capture</a></div>
          </div>
