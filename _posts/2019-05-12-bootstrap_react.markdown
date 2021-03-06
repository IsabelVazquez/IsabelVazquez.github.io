---
layout: post
title:      "Modulo to the Rescue"
date:       2019-05-12 11:02:11 +0000
permalink:  modulo
tags: react bootstrap design
---
![](https://mageewp.com/wp-content/uploads/2015/10/accordions-2.png)
Earlier this year, I ran into an issue where I mapped the backend response (panels) into one column but received feedback that the UI was having odd spacing when one panel was closed. Below are <em>simplified</em> bits of the code that I worked with to give an idea on how to approach this code issue.
### Problematic UI Code
```
 r e n d e r C h i l d r e n   =   ( )   = >   { 
          c o n s t   c h i l d r e n   =   ( f i e l d s ,   m o d e l ,   m o d e l I n d e x )   = >   { 
                r e t u r n   f i e l d s . m a p ( ( f i e l d )   = >   { 
                    r e t u r n   < C o l   s m = { 6 } > 
                                 < F o r m G r o u p > 
                                         < C o n t r o l L a b e l > { f i e l d . l a b e l } < / C o n t r o l L a b e l > 
                                         < I n p u t G r o u p > 
                                                 < F o r m C o n t r o l 
                                                         n a m e = { f i e l d . l a b e l } 
                                                         v a l u e = { f i e l d . v a l u e } 
                                                 / > 
                                         < / I n p u t G r o u p > 
                                 < / F o r m G r o u p > 
                       < / C o l > 
                 } ) 
         } 

      r e t u r n   t h i s . s t a t e .models. m a p ( ( n o d e ,   i n d e x )   = >   { 
              r e t u r n   < C o l   s m = { 6 } > 
                                 <Panel  d e f a u l t O p e n   t i t l e = { n o d e . m o d e l } > 
                                         {   c h i l d r e n ( n o d e . f i e l d s ,   n o d e . m o d e l ,   i n d e x )   } 
                                 < /Panel> 
                 < / C o l > 
          } ) 
 } 

< C o l   c l a s s N a m e = " i n f o "   s m = { 1 2 } > 
     { t h i s . r e n d e r C h i l d r e n ( ) }   
 < / C o l > 
```

In the code above, I was imitating two columns by placing `col-sm-6` columns into one `col-sm-12` column. However, in order to have clearer spacing, I needed to actually implement two columns:
### Solution Part 1
```
<Col sm={12} className="info">
    <Col sm={6}>
        {this.renderChildren(leftElements)}
    </Col>
    <Col sm={6}>
        {this.renderChildren(rightElements)}
    </Col>
</Col>
```

So rather than mapping `this.state.models`, `renderChildren()` would map either of the following parameters: leftElements or rightElements. `this.state.models` is still where the backend response was captured. I ended up using the state with a modulo to create the new parameters.
### Solution Part 2
```
const rightElements = [];
const leftElements= [];
_.forEach(this.state.models, (model, index) =>
    index % 2 === 0 && index !== 0 ?
        rightElements.push(model) :
        leftElements.push(model)
);
```
