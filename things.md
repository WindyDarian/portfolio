### (2016) WebGL Deferred Shading Pipeline Prototype
* Links: [Live Online](https://windydarian.github.io/Project5-WebGL-Deferred-Shading-with-glTF/) | [Video](https://www.youtube.com/watch?v=P-mW_0KRsjo) | [Source Code (GitHub)](https://github.com/WindyDarian/Project5-WebGL-Deferred-Shading-with-glTF)
* Course project using WebGL and JavaScript
* Implemented:
  * Basic __Deferred Shading__ pipeline
  * __Blinn-Phong shading__ with normal mapping
  * __Bloom__ post-processing effect with __two-pass Gaussian blur__
  * __Light proxy__: instead of rendering a scissored full-screen quad for every light, I render __proxy geometry__ which covers the part of the screen affected by a light (using spheres for point lights), thus __reducing wasted fragments in lighting pass__
    * Using __inverted depth test__ with __front-face culling__ to avoid lighting geometries that are far behind the light, thus further reducing wasted fragments. This method increase render speed for 200 point lights to __177%__ compared to regular scissor test optimization
  * __Optimized g-buffer__ from 4*vec4 to 2*vec4 by compressing normal to two floats, increasing framerate to __167%__, see below for details
