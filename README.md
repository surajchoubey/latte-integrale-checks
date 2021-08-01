# LATTE INTEGRALE CHECKS

It contains integration values of Latte-Integrale Software compared with Simple MC Integration. <br/>
Please do have `Latte-Integrale` installed to run the bash scripts `*.sh` files. <br/><br/>

Latte-Integrale Software : https://www.math.ucdavis.edu/~latte/software.php

The test_values function checks values expected and exact from the computed value(`integration_value`). <br/>
```ruby 
test_values(NT integration_value, NT expected, NT exact) 
```

#### To check Answers in latte integrale

1. Clone this repository and `cd` to this directory.
```
git clone https://github.com/surajchoubey/latte-integrale-checks
```
2. Run directly through terminal if you have `latte` installed
```
bash simplex.sh > OUTPUTS/simplex.txt
bash prod_simplex.sh > OUTPUTS/prod_simplex.txt
bash cross.sh > OUTPUTS/cross.txt
bash birkhoff.sh > OUTPUTS/birkhoff.txt
```


Outputs have been extracted as required out from the huge mess of output files and shown here down below.<br/>
The tests values which are there in `simple_mc_integration.cpp` have been put here so you can compare easily with the `latte` values.

Also I havent covered with cubes and rectangles because `latte` cannot support exponential functions ( they were pretty straightforward and can be calculated by hand/calculator even for a 10D function in which variables were separable i.e. `e^(-norm()^2` ) <br />

I have added the `latte` commands too so you can check individually also.




### 1. Simplex Polytopes

For `n` dimensional polytope created `n` dimensional polytope is formed and `n` dimensional function is integrated in here.
```RUBY
test_values(integration_value, 0.67, 0.666);
test_values(integration_value, 0.34, 0.333);
test_values(integration_value, 0.116, 0.1166);
test_values(integration_value, 0.00656, 0.0063492);
test_values(integration_value, 0.000159, 0.000159832);
```

```
integrate --valuation=integrate --monomials=polynomials/1D.polynomial simplex/1D.latte
integrate --valuation=integrate --monomials=polynomials/2D.polynomial simplex/2D.latte
integrate --valuation=integrate --monomials=polynomials/3D.polynomial simplex/3D.latte
integrate --valuation=integrate --monomials=polynomials/5D.polynomial simplex/5D.latte
integrate --valuation=integrate --monomials=polynomials/7D.polynomial simplex/7D.latte
```  

```RUBY
// TEST-1
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 2/3
     Decimal: 0.66666666666666666666666666666667
     Time: 0.00 sec

// TEST-2
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 1/3
     Decimal: 0.33333333333333333333333333333333
     Time: 0.00 sec
     
//TEST-3
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 7/60
     Decimal: 0.11666666666666666666666666666667
     Time: 0.00 sec
     
// TEST-4
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 2/315
     Decimal: 0.0063492063492063492063492063492063
     Time: 0.00 sec

// TEST-5
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 29/181440
     Decimal: 0.00015983245149911816578483245149912
     Time: 0.00 sec
     
```

### 2. Product Simplices

For `n` dimensional polytope created `2n` dimensional polytope is formed and `2n` dimensional function is integrated in here.

```ruby
	test_values(integration_value, 0.334, 0.333);
	test_values(integration_value, 0.0834, 0.0833);
	test_values(integration_value, 0.0110, 0.01111);
	test_values(integration_value, 0.36e-4, 0.36375e-4);
	test_values(integration_value, 0.235e-7, 0.24079e-7);
```

```
integrate --valuation=integrate --monomials=polynomials/2D.polynomial prod_simplex/1D.latte
integrate --valuation=integrate --monomials=polynomials/4D.polynomial prod_simplex/2D.latte
integrate --valuation=integrate --monomials=polynomials/6D.polynomial prod_simplex/3D.latte
integrate --valuation=integrate --monomials=polynomials/10D.polynomial prod_simplex/5D.latte
integrate --valuation=integrate --monomials=polynomials/14D.polynomial prod_simplex/7D.latte
```

```ruby

// TEST-1
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 1/3
     Decimal: 0.33333333333333333333333333333333
     Time: 0.00 sec
     
// TEST-2
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 1/12
     Decimal: 0.083333333333333333333333333333333
     Time: 0.00 sec
     
// TEST-3
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 1/90
     Decimal: 0.011111111111111111111111111111111
     Time: 0.01 sec
     
// TEST-4
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 11/302400
     Decimal: 0.36375661375661375661375661375661e-4
     Time: 0.51 sec
     
// TEST-5
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 11/457228800
     Decimal: 0.24057977100305142633184961227289e-7
     Time: 15.00 sec

```

### 3. Cross Polytopes

For `n` dimensional polytope created `n` dimensional polytope is formed and `n` dimensional function is integrated in here.

```ruby
	test_values(integration_value, 1.334, 1.333333);        // 1st dim
	test_values(integration_value, 1.334, 1.33333);         // 2nd dim
	test_values(integration_value, 0.935000, 0.933333);
	test_values(integration_value, 0.200000, 0.203174);
	test_values(integration_value, 0.020000, 0.020458);
```

```
integrate --valuation=integrate --monomials=polynomials/1D.polynomial cross/1D.latte
integrate --valuation=integrate --monomials=polynomials/2D.polynomial cross/2D.latte
integrate --valuation=integrate --monomials=polynomials/3D.polynomial cross/3D.latte
integrate --valuation=integrate --monomials=polynomials/5D.polynomial cross/5D.latte
integrate --valuation=integrate --monomials=polynomials/7D.polynomial cross/7D.latte
```

```ruby
TEST-1
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 4/3
     Decimal: 1.3333333333333333333333333333333
     Time: 0.00 sec

TEST-2
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 4/3
     Decimal: 1.3333333333333333333333333333333
     Time: 0.00 sec

TEST-3
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 14/15
     Decimal: 0.93333333333333333333333333333333
     Time: 0.00 sec

TEST-4
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 64/315
     Decimal: 0.2031746031746031746031746031746
     Time: 0.02 sec

TEST-5
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 58/2835
     Decimal: 0.020458553791887125220458553791887
     Time: 0.06 sec
```

### 4. Birkhoff Polytopes

For `n` dimensional polytope created `(n-1)^2` dimensional polytope is formed and `(n-1)^2` dimensional function is integrated in here.

```ruby
	test_values(integration_value, 0.67, 0.6666);
	test_values(integration_value, 0.0470, 0.04722);
	test_values(integration_value, 0.000150, 0.000164);
```

```
integrate --valuation=integrate --monomials=polynomials/1D.polynomial birkhoff/2D.latte
integrate --valuation=integrate --monomials=polynomials/4D.polynomial birkhoff/3D.latte
integrate --valuation=integrate --monomials=polynomials/9D.polynomial birkhoff/4D.latte
```

```ruby
TEST-1
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 2/3
     Decimal: 0.66666666666666666666666666666667
     Time: 0.00 sec

TEST-2
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 17/360
     Decimal: 0.047222222222222222222222222222222
     Time: 0.00 sec

TEST-3
Integration of a polynomail as products of linear forms (using the triangulation method)
     Answer: 1643/9979200
     Decimal: 0.00016464245630912297578964245630912
     Time: 0.61 sec

```
