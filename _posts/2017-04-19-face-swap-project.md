---
layout: post
title: Face Swap
date: 2017-04-19 00:00:00 +0200
description: # Add post description (optional)
img: projects/face_swap/face_swap_teaser.jpg # Add image post (optional)
tags: [Face Swap] # add tag
type: project
---
Swapping faces means transferring a face from a source photo onto a face appearing in a target photo, attempting to generate realistic, unedited looking results.
This project implements an image-to-image face swapping pipeline as described in [our paper](https://arxiv.org/abs/1704.06729).

Code has been made available at: [https://github.com/YuvalNirkin/face_swap](https://github.com/YuvalNirkin/face_swap)

## Face Swapping Pipeline
In the first stage of the pipeline we treat both input images, the source image and the target image, the same way:
- 3D reconstruct the face shape from a single image.
- Compute the face landmarks for finding the initial pose of the face.
- Fit the face shape to the face expression.
- Compute the face segmentation.

In the final stage we compute a texture from the source image, wrap it on it's corresponding 3D shape and transfer it to the target image.
The output image is comprised from the rendered image from the last step, blended with the target image.

![Face Swap Pipeline]({{site.baseurl}}/assets/img/projects/face_swap/face_swap_pipeline.png)