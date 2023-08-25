---
title: "A Bee or Not a Bee?"
date: "2023-24-08"
draft: true
socialShare: true
math: true
gradio: true
---

{{< warning Disclaimer>}}
This is a demo model - use at your own risk. Stay safe out there, don't get stung!
{{< /warning >}}

<br>

Bees, wasps, and hoverflies look pretty similar. It can be easy to forget who's who. Hover flies don't sting! Bees pollinate flowers, and make honey. Wasps well... Let's just hope they're doing their bit. 

I trained an image classifier that can help. It's **95 % accurate** on my validation set! **Note:** pictures from your camera will be a little harder.

## Try it out!

Here is a [link to a demo on my Huggingface spaces](https://huggingface.co/spaces/Ben-orli/a-bee-or-not-a-bee) with demo images you can drag and drop, or upload your own images. I highly recommend clicking the link as it's fun an intuitive.

If you love this site so much you don't want to leave, please don't fear, you can upload your images with the button below:

{{< beeupload >}}

This button accesses my model through an API and passes the result right back to you here on the site.

## Info for Nerds

The classifier is a neural network I **trained locally on my GPU** using **fastai/PyTorch**. I downloaded the images **from DuckDuckGo using Python** then cleaned the images myself—turns out there are a lot of cartoon bees on the internet. I was able to train it to 95 % accuracy using under 600 images using a combination of **data augmentation** and **transfer learning**.