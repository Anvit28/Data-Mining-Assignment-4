## Problem 3: Association rules for grocery purchases

Dataset: groceries.txt

We take a look at the dimensions of this data:

    ## [1] 9835  169

This means we have 9835 transactions and 169 distinct items.  
The top 10 most items in terms of abosolute frequencies are:-  
![](Problem-3_files/figure-markdown_strict/3.top%2010%20abosolute%20frequencies-1.png)
The top 10 most items in terms of relative frequencies are:-  
![](Problem-3_files/figure-markdown_strict/3.top%2010%20relative%20frequencies-1.png)
The next step is to analyze the rules using the A-Priori Algorithm. We
picked the thresholds of support as 0.005, confidence as 0.1 and lift
as 1. We chose the support threshold as 0.005 as we wanted to capture
rules of only those items that have popularity of at least 0.5%. We
chose the threshold of confidence as 0.1 as we are interested in only
those (X,Y) pairs such that the Prob(Y|X) is at least 10%. We chose lift
threshold to be 1 as it is the traditional threshold that implies which
implies that item Y is likely to be bought if item X is bought.

Now we plot all the rules in (support, confidence) space.  
![](Problem-3_files/figure-markdown_strict/3.plotting%20in%20(support,%20confidence)%20space-1.png)
We can notice from the above graph that the high lift rules tend to have
low support.  
Similarly, we plot all the rules in (support, lift) space.  
![](Problem-3_files/figure-markdown_strict/3.plotting%20in%20(support,%20lift)%20space-1.png)
The top 10 rules based on the confidence are-

    ##      lhs                     rhs                    support confidence    coverage     lift count
    ## [1]  {root vegetables,                                                                           
    ##       tropical fruit,                                                                            
    ##       yogurt}             => {whole milk}       0.005693950  0.7000000 0.008134215 2.739554    56
    ## [2]  {other vegetables,                                                                          
    ##       pip fruit,                                                                                 
    ##       root vegetables}    => {whole milk}       0.005490595  0.6750000 0.008134215 2.641713    54
    ## [3]  {butter,                                                                                    
    ##       whipped/sour cream} => {whole milk}       0.006710727  0.6600000 0.010167768 2.583008    66
    ## [4]  {pip fruit,                                                                                 
    ##       whipped/sour cream} => {whole milk}       0.005998983  0.6483516 0.009252669 2.537421    59
    ## [5]  {butter,                                                                                    
    ##       yogurt}             => {whole milk}       0.009354347  0.6388889 0.014641586 2.500387    92
    ## [6]  {butter,                                                                                    
    ##       root vegetables}    => {whole milk}       0.008235892  0.6377953 0.012913066 2.496107    81
    ## [7]  {curd,                                                                                      
    ##       tropical fruit}     => {whole milk}       0.006507372  0.6336634 0.010269446 2.479936    64
    ## [8]  {citrus fruit,                                                                              
    ##       root vegetables,                                                                           
    ##       whole milk}         => {other vegetables} 0.005795628  0.6333333 0.009150991 3.273165    57
    ## [9]  {other vegetables,                                                                          
    ##       pip fruit,                                                                                 
    ##       yogurt}             => {whole milk}       0.005083884  0.6250000 0.008134215 2.446031    50
    ## [10] {domestic eggs,                                                                             
    ##       pip fruit}          => {whole milk}       0.005388917  0.6235294 0.008642603 2.440275    53

We graphically visualize the top 10 rules by the following graphs-  
![](Problem-3_files/figure-markdown_strict/Visualization%201-1.png)
![](Problem-3_files/figure-markdown_strict/Visualization%202-1.png)
![](Problem-3_files/figure-markdown_strict/Visualization%203-1.png) We
can see from the above plots that fruits, vegetables and dairy products
are the most common grocery items. We can see that if a person bought
fruits, vegetables and dairy products; it is very likely for us to see
them adding whole milk in his/her basket as well. We can also see that
if a person bought citrus fruit, root vegetables, and whole milk; it is
very likely for us to see them adding other vegetables in his/her basket
as well.  
The above discoveries make perfect sense as these are very common
grocery items and this behavior is often observed in the grocery stores.
