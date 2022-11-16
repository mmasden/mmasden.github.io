---
layout: post
title: "Using 'Good Questions' for Inquiry in Multivariable Calculus"
categories: teaching
mathjax: true
---

I am a huge fan of the [Good Questions Project](http://pi.math.cornell.edu/~GoodQuestions/materials.html) and "Just-in-Time-Teaching." Here's one place where I've put that into practice.

## Building a conceptual understanding of the gradient

Before this activity, in a previous class, I introduced \\(\nabla f(x,y,...) = \langle f_x, f_y,... \rangle\\) after discussing how it shows up when we compute directional derivatives at a point: \\(f_{\vec u} = \nabla f \cdot \vec u\\) for any direction vector \\(\vec u \\). I demonstrated some properties of the gradient, namely, that if \\(\vec u\\) was tangent to a level curve or level surface we expect \\( \nabla f \cdot \vec u = 0 \\), and as a result (my students pointed this out at this point, not me!) \\( \nabla f\\) gives a normal vector to a level surface at a point, and can be used to find a tangent plane. It also points in the direction of fastest increase, because \\( \nabla f \cdot \vec{u} = \Vert \nabla f \Vert \Vert \vec u \Vert \cos \theta \\) is maximized when \\(\theta=0\\). 

I wanted to have my students reflect on this material for their upcoming exam, tie this information back in to their knowledge of partial derivatives, reiterate the relationship between gradients and level curves before we do Lagrange multipliers, and foreshadow what's coming up most imminently: multivariable optimization. 

I gave this activity as a think-pair-share exercise and it ended up taking about half of the 50-minute class period to complete and discuss. I'm willing to call this inquiry learning, because even though I had explicitly told my students some of the facts which are useful for this activity, many students were gone for part or all of the earlier lecture, and we ended up re-deriving many of these properties as a class as they worked through these problems. With slight reordering (putting question 4 at the beginning) it would be reasonable to do this activity immediately after introducing the definition of the gradient and its relationship to computing directional derivatives, leading in to then discussing the properties of the gradient. Finally, my students actively discovered that local maxima and saddle points seem to occur when \\( \nabla f = 0\\). It's all worth it if it means my students don't rely on memorizing steps to solve their optimization questions. 

**Check in: Consider the contour diagram of a function \\(f(x,y)\\) below. Assume it shows the general behavior of the function, and lighter regions indicate higher function values.**

<img src="../../assets/images/blog/contour.png" width="70%" style=" display: block;
                                                                    margin-left: auto;
                                                                    margin-right: auto;">

1. Sketch a picture of \\(\nabla f \\) at each of the points \\(P,Q,R\\). 
2. Rank \\(P,Q\\) and \\(R\\) in the order of increasing magnitude of the gradient, \\(\Vert \nabla f \Vert \\). 
3. There are three points on \\(f(x,y)\\) where \\(\nabla f = \vec 0\\). Approximately where should they occur? 
4. At each point \\(P,Q,R\\), determine if \\(f_x\\) and \\(f_y\\) are approximately negative, positive, or zero. 

