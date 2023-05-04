

<h1 align="center">AutoColor: Learned Light Power Control for Multi-Color Holograms</h1>

 <p align="center">

  <img width ="12%" src="https://complightlab.com/people/yicheng_zhan.png">
  <img width ="12%" src="https://complightlab.com/people/koray_kavakli.png">
  <img width ="12%" src="https://github.com/complight/complight.github.io/blob/master/docs/people/hakan_urey.png?raw=true">
  <img width ="12%" src="https://raw.githubusercontent.com/complight/autocolor_/main/qi_sun.png">
  <img width ="12%" src="https://user-images.githubusercontent.com/46696280/214999478-ea45353d-3704-4290-8e90-10c747887253.png">
 </p>


 <h4>
  <p align="center">
    <a href="https://github.com/AlberTgarY">Yicheng Zhan<sup>1,*</sup></a> |
    <a href="https://github.com/KorayKavakli">Koray Kavakli<sup>1,2</sup></a> |
    <a href="https://www.linkedin.com/in/hakan-%C3%BCrey-1386a9a/?originalSubdomain=tr">Hakan Ürey<sup>2</sup></a> |
    <a href="https://engineering.nyu.edu/faculty/qi-sun">Qi Sun<sup>3</sup></a> |
    <a href="https://kaanaksit.com/">Kaan Akşit<sup>1,*</sup></a>
   </p>
 </h4>
 
   <h4>
   <p align="center">
    <strong>   <sup>1</sup>University College London, <sup>2</sup>Koc University</strong>, <sup>3</sup>New York University
   </p>
  </h4>


   <p align="center">
    <img width ="2%" src="https://user-images.githubusercontent.com/46696280/215226725-5fad80c7-c795-4054-8279-c9789ec59795.png"> 
    <a href="https://complightlab.com/">UCL Computational Light Laboratory</a> 
   </p>

  
<h2>
 <p align="center">
   <a href="https://arxiv.org/abs/2305.01611">Paper</a> |
   <a href="https://github.com/complight/autocolor">Code</a> 
 </p>
</h2>

<!-- <h3>
 <p align="center">
   <a> Optics Express 2023 </a> 
 </p>
</h3> -->

  
 <p align="center">
  <img width="700" src="https://raw.githubusercontent.com/complight/autocolor_/main/schematic.png">
 </p> 
 
 <h2>
 <p align="center">
    Abstract
 </p>
 </h2>
   
Multi-color holograms rely on simultaneous illumination from multiple light sources. These multi-color holograms could utilize light sources better than conventional single-color holograms and can improve the dynamic range of holographic displays. In this letter, we introduce AutoColor, the first learned method for estimating the optimal light source powers required for illuminating multi-color holograms. For this purpose, we establish the first multi-color hologram dataset using synthetic images and their depth information. We generate these synthetic images using a trending pipeline combining generative, large language, and monocular depth estimation models. Finally, we train our learned model using our dataset and experimentally demonstrate that AutoColor significantly decreases the number of steps required to optimize multi-color holograms from > 1000 to 70 iteration steps without compromising image quality.

 <h2>
 <p align="center">
    Methodology
 </p>
 </h2>

#### Generative model and large language model
By using the Large Language Model (LLM) called GPT-4 via its online interface ChatGPT, we generate a series of detailed prompts with different keywords. We used a set of prompts to guide the generation process and developed a large dataset of images locally using text-to-image generation models and a super-resolution network. We estimated the depth information for the generated images using a monocular depth information network and optimized multi-color holograms and their light source powers using a HoloHDR optimization pipeline. The entire [dataset](https://github.com/complight/hologram_dataset/tree/main/diffusion) generation process was computationally intensive and took about ten days using multiple GPUs.

#### Multi-color holograms
We used [HoloHDR](https://complightlab.com/publications/holohdr) to generate multi-color holography and uses a CNN to estimate light source power from input images. The estimated light source powers are then used to optimize multi-color holograms using an existing pipeline. We validate the approach experimentally and show that AutoColor can significantly improve computational efficiency by reducing the optimization steps. 

We also developed a holographic display hardware prototype for quantitative evaluation and summarize our quantitative evaluation in the below figure.

 <h2>
 <p align="center">
    Result
 </p>
 </h2>  
 
We demonstrate that this approach requires significantly fewer steps and can lead to holograms with wide dynamic ranges at interactive rates. The approach is validated through experimental analysis, and we suggest that AutoColor represents a promising research frontier for future hologram development.
<br />
 <p align="center">
  <img width="900" src="https://github.com/complight/autocolor_/blob/main/result.png?raw=true">
 </p> 


## Citation
```bibtex
@misc{zhan2023autocolor,
      title={AutoColor: Learned Light Power Control for Multi-Color Holograms}, 
      author={Yicheng Zhan and Koray Kavaklı and Hakan Urey and Qi Sun and Kaan Akşit},
      year={2023},
      eprint={2305.01611},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}

```
## Relevant research works
Here are relevant research works from the authors:

- [HoloHDR: Multi-color Holograms Improve Dynamic Range](https://complightlab.com/publications/holohdr/)
- [Realistic Defocus for Multiplane Computer-Generated Holography](https://complightlab.com/publications/realistic_defocus_cgh/)
- [Optimizing Vision and Visuals: Lectures on Cameras, Displays, and Perception](https://complightlab.com/teaching/siggraph2022_optimizing_vision_and_visuals/)
- [Odak](https://github.com/kunguz/odak)


## Contact Us
    Please reach us through [email](mailto:k.aksit@ucl.ac.uk) to provide your feedback and comments.

## Acknowledgements
Kaan Akşit, Koray Kavaklı and Yicheng Zhan are supported by the Royal Society’s RGS/R2/212229
Research Grants 2021 Round 2 and Meta Reality Labs inclusive rendering initiative 2022. 

Hakan Urey
is supported by the European Innovation Council’s HORIZON-EIC-2021-TRANSITION-CHALLENGES
program Grant Number 101057672 and Tübitak’s 2247-A National Lead Researchers Program, Project
Number 120C145. 

Qi Sun is partially supported by the National Science Foundation (NSF) research grants
#2225861 and #2232817.

