---
layout: single
title: Research
permalink: /research/
author_profile: true
type: pages
scope:
    path: ""
    type: pages
toc: true
toc_label: "Research"
header:
  overlay_image: /assets/images/sunset-gsl.jpg
---

## Cosmic-Ray Energy Spectrum

![image-left](/assets/images/bdt-small.png){: .align-right} Cosmic rays are charged particles
(e.g. protons, alpha particles, iron nuclei, etc.) originating from outer space. I focus on
 applying unfolding (deconvolution) techniques to data collected with the IceCube South Pole Neutrino Observatory to study the composition of cosmic-rays at high energies. 
A better  understanding of the cosmic-ray energy spectrum can help answer fundamental questions related to the origin of cosmic rays.
<img align="" src="http://latex.codecogs.com/svg.latex?N_{\text{side}} = 256" style="border: 0;"/>


<?php 

//Latex php string variable
function latexString($eq_string,$align=""){
  //$ls="<img src=\"http://latex.codecogs.com/svg.latex?$eq_string\" style=\"border: 0;\"/>";
  $ls="<img align=\"$align\" src=\"http://latex.codecogs.com/svg.latex?$eq_string\" style=\"border: 0;\"/>";
  return $ls;
}

//Simple print function for latex equation
function printLatex($eq_string){
  $LS = latexString($eq_string);
  echo("$LS");
//echo("<img src=\"http://latex.codecogs.com/svg.latex?$eq_string\" style=\"border: 0;\"/>");
//echo("&nbsp <img src=\"http://latex.codecogs.com/svg.latex?$eq_string\" style=\"border: 0;\"/>");
}

//Nice formating for html printing of latex equations
//If a list, then bullet point, otherwise, pad nicely with newlines
function latexFunc($eq){
  if (is_array($eq)){
    echo("<ul>");
    foreach ($eq as &$eq_string){
      // Make a bullet list
      echo("<li>");
      printLatex($eq_string);
      echo("</li>");

      // Only extra newline if not last element
      if ($eq_string !== end($eq))
      {
        echo("<br/>");
      }
    }
    echo("</ul>");
  }
  else{
    // Otherwise, just print the equation comfortably
    echo("<br/>");
    echo("<br/>");
    echo("&nbsp&nbsp&nbsp&nbsp");
    printLatex($eq);
    echo("<br/>");
  }
}

?>

<?php printLatex("N_{\text{side}} = \\alpha"); ?>

{: .text-left}
