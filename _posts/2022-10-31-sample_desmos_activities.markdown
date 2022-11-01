---
layout: post
title: "Sample Desmos Activities"
categories: teaching
mathjax: true
---

I use Desmos activities and graphs as a constructivist tool to allow my students to experiment and draw their own connections in mathematics. I will update this page with additional examples over time.


## Function Transformations 

*This activity is appropriate in precalculus, after students have already explored individual horizontal and vertical transformations, and are ready to analyze a sequence of multiple transformations.*

The solid graph of the function \\(f(x)\\) is shown below. The dashed graph is a second function, \\(g(x)\\), which is a transformation of \\(f(x)\\). 

Find an expression for \\(g(x)\\) *in terms of* \\(f(x)\\). You can check your work by changing the expression in the Desmos graph below.

You may wish to try changing one thing at a time. Remember, what is the difference between \\(f(x+1)\\) and \\(f(x)+1\\)? What is the difference between writing \\(f(-2x)\\) and \\(-2f(x)\\)? You will need to use several transformations. 

<div class="desmos-border">
		<div id="function-transformations" class="desmos-container"></div>
</div>
	
<script src="https://www.desmos.com/api/v1.7/calculator.js?apiKey=dcb31709b452b1cf9dc26972add0fda6"></script>

<script>
    const DESMOS_PURPLE = "#6600cc";
    const DESMOS_BLUE = "#0087cc";
    
    
    
    let data =
    {
        "function-transformations":
        {
            bounds: {left: -5, right: 5, bottom: -5, top: 5},
            
            expressions:
            [
                {latex: String.raw`f(x)=\{x<0:-x, x>= 0: x^{2}\}`, color: DESMOS_PURPLE, secret:true},
                {latex: String.raw`-2f(1-x)+3`, color: DESMOS_PURPLE, lineStyle: Desmos.Styles.DASHED, secret:true},
                {latex: String.raw`f(x)`, color: DESMOS_BLUE},
                //{latex: String.raw`a=5`, sliderBounds: {min: 0, max: 10, step: 1}},
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