# Images! 

Experiments and algorithms in image processing, computer vision, and computational photography! Projects inspired by personal curiosity, classes, and the [Udacity computational photography course](https://www.udacity.com/course/computational-photography--ud955) offered at Georgia Tech as CS 6475. 

## [Seam Carving] (https://github.com/momonala/imaging_and_vision/tree/master/seam_carving)

My first experiment with a technique that looks like magic. Content-Aware Image Resizing technique was invented by Avidan and Shamir from Mitsubishi Electric Research Labs in 2007. 

My implementation: https://www.youtube.com/watch?v=gIVqbKQdSGs	

I used python's openCV and scikit image to build a few seam carving algroithms. The first, seam_carving_slider.py, is a tool that allows the user to upload an image and use a trackbar to compress the image as desired. My second algorthim, seam_carving_iter.py is a loop implementation that allows the user to input a percent of the original image to compress into, and save consecutive images as one seam is removed per iteration. My algorithm takes in inputs for direction,  compression ratio and number of seams per iteration. Hardcoded is the energy mapping function, which does Gaussian smoothing and measures the Sobel gradient magnitude in openCV, much faster than scikit. In the loop I recursively carve (scikit) and recompute the energy map which makes the seam cutting more seamless. 

## [Image Layering with Open Source NASA Map Images] (https://github.com/momonala/Earth-Layers)

The code works as a series of transformations and image overlays on Equirectangular maps. I used population data and Earth at Night (lights) data. You can adjust the parameters of one image to highlight certain aspects of the image data, and overlap images to see how various features interact.

<img src="https://raw.githubusercontent.com/momonala/imaging_and_vision/master/earth_layers/earth_layers2.jpg" width="480" alt="Combined Image" />

## Cell Counting with Hough Circles 

I built a pretty in depth pipeline to detect cells on a 96 well-plate agar dish. This was for a project at work which involved a larger pipeline of cell counting and colony picking with a robot. My algorithm vastly improved the existing default technique. I included parameters to filter the desired radius size of the cell, the separation of cells within each plate (close-by cells can otherwise be incorrecly grouped as the same colony, even though they have genetic differences. This avoids that), and had an overall higher accuracy at finding cells. It was based on using Hough Circles as the shape finding algorithm, with a whole lot of numpy to itemize the well plates and cell ranking. 