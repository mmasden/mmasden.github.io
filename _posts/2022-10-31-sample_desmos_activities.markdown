---
layout: post
title: "Sample Desmos Activities"
categories: teaching
---

I use Desmos activities and graphs as a constructivist tool to allow my students to experiment and draw their own connections. 


## Function Transformations

The solid graph of the function $f(x)$ is shown below. The dashed graph is a second function, $g(x)$. 

Try using function transformations to find an expression for $g(x)$ in terms of $f(x)$.

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