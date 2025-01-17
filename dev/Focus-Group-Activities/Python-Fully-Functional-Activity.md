---
sort: 1
---

# Fully Functional Python Activity

<!-- **Definition: ** -->

## Background

Stars are hot balls of gas and light held together by gravity. At the core, light elements such as hydrogen and helium are fused to create heavier atoms. This fusion releases an enormous amount of energy that is transported away by photons leaving the star.

While this may seem straightforward enough, the mechanisms that tell us how the photons move from the center of the star to the edge can actually get pretty complex. The main issue is that photons can't move in a straight path from the center of a star to its edge — there are many tiny gas particles in their way. Instead, each photon makes quick jumps, bouncing between gas particles like a pinball in an arcade machine, slowly working its way away from the core.

## The Activity

In this activity, we are going to explore a model of a star where we can examine the true path that a photon takes to escape. We will utilize a model built in Python and use it to discover some fundamental properties of photons and stars. Before we start, take a moment to complete this <a href="https://forms.gle/1eUWGcZpXcRVj8197" target="_blank">Pre-Activity Survey</a> with your group

### The Model

The model (<a href="https://colab.research.google.com/github/alexdelfranco/astronomy-guide/blob/master/Focus-Group-Activities/Random-Walk-Scaffolded.ipynb" target="_blank">linked here</a>) has two main sections. The first section, titled "Model Setup" is made up of some imports and two functions that compute the math and visual for the model. Run those cells and then move to the section titled "Running the Model." When you run the cell, you'll see a blue circle which is a 2D cross section of a star.

Inside the star, we can see a plot of the path that the photon took while moving through the star. When you run the cell, the model simulates the random path the photon takes on its way out of the star. The number in the title of the plot tells you the total number of steps the photon has travelled.

The default radius of the star is 100, which you can change by altering the number after `radius=` in the code cell you just ran. As the photon moves, the length of each of its steps is set by the number after `step_length=`. We can assign units to both of these values later in the activity.

Run the model again and talk to your partner about what you see. If the plotting extensions loaded correctly, you can click the button with the square box on the left of the plot and then select a region inside the star to zoom in on. Play around with the model and see if it works like you expect.

As you experiment with the model, discuss the following questions with your partner.

**What is the squiggly blue line inside the star? Why does it look like that?**

**Why does the photon start its path at the center of the star?**

**Why does the model choose a random direction for the photon at each step?**

**Will the length of each step be the same for every star? Why or why not?**

Take a few more minutes to play around with the model. Talk to your partner about how to use it and what you are learning.

## Conceptual Questions (Discussions with your activity partner)

### Reflecting on The Model

As you run the model, the photon takes a jittery path from the core of the star to its edge. Explain to your activity partner briefly in your own words why the photon takes this path instead of a straight one out of the star.

A photon moving out of the Sun with no resistance should escape the Sun in less than 5 seconds. Based on what you have seen by running a real physical model of a photon traveling through a star, estimate again how long you think it would take a photon making this “random walk” to escape? (Each of you should make your own estimate.)

*It’s worth noting two differences between the model and real life. First, in a star like the sun, the average path length of a photon is about 1mm, which means by default we are assuming the radius of the star in the model is around 100mm. Of course that isn’t a good estimate for the entire star, but it actually is a pretty good model of what is happening in a small sphere inside the star. If we assume the physics are the same for the rest of the star (which they mostly are!) the model does a pretty good job.*

*Second, it is worth noting that the model assumes the same step length each time the photon moves. In reality, this is an average step length. There is a lot of randomness inside of stars — sometimes the photon barely jumps and sometimes it jumps a lot! But the step length (often referred to scientifically as the “mean free path” which just means the average unobstructed path of the photon) is still a really good estimate of the photon’s average step size!*

### A Photon Escaping the Sun

We want to find how long it takes a real photon to escape the Sun. Let's assume the step length in the model is equal to 1 mm (which is pretty accurate for the Sun). Set the radius of the star to equal the Sun's radius in millimeters (\\(R_{\odot} = 7*10^{11}~mm\\)). Now run the model. What do you see happening? Is it possible to use this simulation to answer this question directly? Why or why not??

Hmm. Maybe we could find a relationship between the straight line distance the photon traveled (here the radius of the star) and the number of steps the photon takes to escape? Try a few different values (0.5, 1, 2, 3, and 5) for the average photon path length (by changing the number in the cell where you run the model) and observe how many steps it takes for the photon to escape. Run the model 3-5 times for each value of the path length and record the average number of steps (\\(N\\)) it takes the photon to escape the star for each path length.

The number of steps a photon takes is related to the ratio between step length and the radius of the star. What is the approximate relation between \\(\dfrac{r}{l}\\) and \\(N\\) (where \\(r\\) is the radius of the star and \\(l\\) is the step length of the photon)? *Hint: The relation should take the form of a power law: \\(N = \(\dfrac{r}{l}\)^x\\) where \\(x\\) is some positive integer. Use the data you collect to find \\(x\\). Try plotting your points and drawing a curve through them. It’s ok if the curve doesn’t hit every point that you measured — it should go through the average of them all. See if you can use the curve to find an integer value for \\(x\\). Also note that we made the radius \\(r\\) equal to 100 when building the model.*

Now use your relation between \\(\dfrac{r}{l}\\) and \\(N\\) to calculate the number of total steps a photon needs to take to escape from the Sun. *Note: You can create new cells to add any equations or expressions to help you answer this question.* (For \\(l\\) use \\(1~mm\\) and for \\(r\\) use the radius of the Sun measured in millimeters from your equation sheet.) 

Given the number of steps you estimated, now find how long it takes the photon to escape from the Sun. Does the answer surprise you? Why or why not?

### An Improved Model

The path length of a photon is affected by two physical properties of a star: the spacing of particles in the star (density) and the likelihood that each particle will interfere with the photon (not all particles interact with and redirect light in the same way). The chance that a particle will redirect (or scatter) a photon is called the “opacity”. A high average opacity in a star means a high chance of light scattering off particles (which leads to a low step length) and a low opacity means a low chance of scattering (leading to a higher step length).

When either of these two factors increase (i.e. when the density or the opacity go up), the path length of the photon decreases. Thus we can reason that density and opacity are both inversely related to the path length.

This means we can write an equation for \\(l\\) (which just represents step length). If we call density \\(d\\) and opacity \\(k\\), we can write the value for \\(l\\) using the equation:

$$ l = \dfrac{1}{dk} $$

It turns out that the model already includes density and opacity. Replace the `step_length=` input in the model with `opacity=` and `density=`, both separated by a comma. Then input values for both and run the model. If you specify both an opacity or density and a step_length, the model will get confused and print an error message.

---

Try running the model a few times with different values of density and opacity. What do you notice about the movement of the particle when you make these changes? Use the plotting add ons to zoom in on the individual steps of the particle. Does a higher opacity lead to a shorter or longer escape time? What about a higher density? Do these conclusions make sense? Discuss with your activity partner.

### Putting It All Together

Using your relation between path length and escape time that you found earlier, estimate by what factor the escape time would change if the density of the star was doubled? What about if the opacity was doubled? What if the radius was doubled?

Try sketching the relationships between the key physical properties here. Make three graphs, one with density on the x-axis, one with opacity on the x-axis, and one with radius on the x-axis. Put escape time on the y-axis for all three and then plot a handful of values until you have a general relation. Are the relations intuitive? Explain to your activity partner why your curves have the shapes they do.

## Finishing

Nice work!! You just used a complete model of the interior of a star. That's no small accomplishment. As a group, reflect on what you learned by filling out this <a href="https://forms.gle/bWhYqAeFMbKfsL286" target="_blank">Post-Activity Survey</a>. Then head over to the main table for a final discussion.