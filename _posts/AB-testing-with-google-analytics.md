---
layout: post
title: 'A/B testing with Google Analytics '
date: 2017-01-20 08:32:18 -0700
summary: This is an empty post to illustrate the pagination component with Pixyll.
published: true
---
I like a quote from an article by Amy Gallo in HBR, where she interviewed a guy called [Kaiser Fung](http://www.kaiserfung.com/) and he defines, simply, what is the nature of an A/B test. When asked about the test, Fung says it clearly:

> _"A/B testing can be considered the most basic kind of randomized controlled experiment"_


By randomized, he is refering to the fact that you can experiment with multiple features on an A/B test. You could change a title, you could change an image, you could change everything - and that's way is randomized. 

And it's controlled, because you do need a control group to run the test and compare with the results later. If you want to know a little more, make sure you read the whole article [here](https://hbr.org/2017/06/a-refresher-on-ab-testing).

In this little tutorial, I'm gonna show you how simple is to set this sort of test using the number 01 analytics tool for web: **Google Analytics.**


## Set the test in 3 little steps:

1. Create Experiment
2. Set the Orignal and the Variations URLs
3. Insert the Code 

My test here is based on the classic blue vs. red buttom battle. 

I want to know which one will increase our CTR. So I already have 2 urls with the different buttom colors: the blue one is the original with the url **/produtos/adk/** and I created a copy with a different buttom color on **/produtos/adk-2/**. Let's do this. 

## Step 1: Create Experiment 
Over to your Analytics Dashboard, go to **Behaviours** and then **Experiments** on your sidebar. This is also how you gonna get to your experiments later, when you set'em up. 

Now, go to **Create Experiment** and complete informations like name and the goal of the test. If you haven't created a goal yeat, you'll be able to create one just right up. 

## Step 2: Set the Original and the Variations URLs 
This is simple: you'll only need to **copy and paste the URLs** and set how many variations you have. I only had one, because I only wanted to analyze the effectiveness of the buttom color. Peharps I could create anoter variation with no buttom at all, but with another CTA? That's something to think about. 


## Step 3: Time to Insert the Codes
Make sure all the pages have the basic Analytics code running, first. After that, select **"Manually insert the code"** to copy the code and install the experiment code snippet right after the <head> tag of your **Original Page**. 
  
  
After you've saved, click on **Next** and GA will check if everything is in place. All you need now is to **Start Experiment**and GA will route visitors to the varitions and record the effectiveness.:+1:
<br>
<br>
<br>
I made a little video:

<center>Literally, less than 5 minutes</center> 
<br> <br> <br> 
Well, this is it for now.<br> <br> <br> 
Peharps on the next post I will show the results and data analysis?<br> 
See ya!
