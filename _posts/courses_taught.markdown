---
layout: post
title: "Courses Taught"
categories: ["misc"]
---

### Courses

*In the capacity of Instructor of Record:*

* Math 111 (College Algebra)
* Math 112 (Elementary Functions)
* Math 231 (Elements of Discrete Mathematics I) 
* Math 243 (Intro. to Methods of Probability and Statistics)
* Math 251 (Calculus I)

*In the capacity of Graduate Assistant/Marker*: 

* Math 243 (Intro. to Methods of Probability and Statistics)
* Math 461 (Introduction to Mathematical Methods of Statistics I) 
* Math 635-636 (Algebraic Topology)

### Teaching Seminar

I co-organize the [Student Teaching Seminar](https://math.uoregon.edu/seminars) for mathematics graduate students at the University of Oregon, together with [Greg Knapp](https://pages.uoregon.edu/gknapp4/index.html). 

### Desmos 

<div class="desmos-border">
		<div id="taylor-series" class="desmos-container"></div>
	</div>
	
<script src="https://www.desmos.com/api/v1.7/calculator.js?apiKey=dcb31709b452b1cf9dc26972add0fda6"></script>

<script>
    const DESMOS_PURPLE = "#6600cc";
    const DESMOS_BLUE = "#0087cc";
    
    
    
    let data =
    {
        "taylor-series":
        {
            bounds: {left: -10, right: 10, bottom: -10, top: 10},
            
            expressions:
            [
                {latex: String.raw`f(x)=\{x<0:-x, x>= 0: x^{2}\}`, color: DESMOS_PURPLE, secret:true},
                {latex: String.raw`f(x)+1`, color: DESMOS_BLUE},
                {latex: String.raw`a=5`, sliderBounds: {min: 0, max: 10, step: 1}},
            ]
        }
    };
    
    create_desmos_graphs(data);
    
    
    function create_desmos_graphs(data)
    {
        document.querySelectorAll(".desmos-container").forEach(element =>
        {
            let calculator = Desmos.GraphingCalculator(element, {
                keypad: false,
                settingsMenu: false,
                zoomButtons: false,
                showResetButtonOnGraphpaper: true,
                border: false,
                expressionsCollapsed: true,
                
                xAxisMinorSubdivisions: 1,
                yAxisMinorSubdivisions: 1
            });
            
            data[element.id].expressions.forEach(expression =>
            {
                expression.latex = expression.latex.replace(/\(/g, String.raw`\left(`);
                expression.latex = expression.latex.replace(/\)/g, String.raw`\right)`);
                
                expression.latex = expression.latex.replace(/\[/g, String.raw`\left[`);
                expression.latex = expression.latex.replace(/\]/g, String.raw`\right]`);
            });
            
            calculator.setMathBounds(data[element.id].bounds);
            
            calculator.setExpressions(data[element.id].expressions);
            
            calculator.setDefaultState(calculator.getState());
        });
    }
</script>