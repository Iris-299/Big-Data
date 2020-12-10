# Amortized Analysis

## Agggregate Method
   
**Amortized cost**:   Give a sequence of n operations, the amortized cost is    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;<u>Cost(_n_ operations)</u>   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;~~&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;~~   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_n_   
  
## Banker's Method  

Chrge 3 for each insertion. 1 coin is the raw cost for insertion.    
· Resize needed: To pay for moving the elements, use the coin that's present on each element that needs to move.    
· Place one coin on the newly-inserted element, and one coin capacity/2 elements prior.

## Physicist's Method 

* Define a potential function, 𝛷 which maps states of the data structure to integers:    
  ·𝛷(h<sub>0</sub>) = 0   
  ·𝛷(h<sub>t</sub>) ≥ 0    
* amortized cost for operation t:   
  c<sub>t</sub> + 𝛷(h<sub>t</sub>) - 𝛷(h<sub>t-1</sub>)

* if c<sub>t</sub> is small, the potential increases  
  if c<sub>t</sub> is large, the potential decreases by the same scale

* The cost of n operations is <a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^n{c_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^n{c_i}" title="\sum_{i=1}^n{c_i}" /></a>   
* The sum of the amortized cost is:   
  &emsp;&emsp;&emsp;<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^n{(c_i&plus;\phi(h_i)-\phi(h_{i-1}))}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^n{(c_i&plus;\phi(h_i)-\phi(h_{i-1}))}" title="\sum_{i=1}^n{(c_i+\phi(h_i)-\phi(h_{i-1}))}" /></a>   
  &emsp;&emsp;&emsp;= c<sub>1</sub> + 𝛷(h<sub>1</sub>) - 𝛷(h<sub>0</sub>) +  c<sub>2</sub> + 𝛷(h<sub>2</sub>) - 𝛷(h<sub>1</sub>)···+ c<sub>n</sub> + 𝛷(h<sub>n</sub>) - 𝛷(h<sub>n-1</sub>)   
  &emsp;&emsp;&emsp;<a href="https://www.codecogs.com/eqnedit.php?latex==\phi(h_n)-\phi(h_0)&plus;\sum_{i=1}^n{c_i}&space;\geq&space;\sum_{i=1}^n{c_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?=\phi(h_n)-\phi(h_0)&plus;\sum_{i=1}^n{c_i}&space;\geq&space;\sum_{i=1}^n{c_i}" title="=\phi(h_n)-\phi(h_0)+\sum_{i=1}^n{c_i} \geq \sum_{i=1}^n{c_i}" /></a>   
  
