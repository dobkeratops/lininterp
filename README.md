generic linear interpolation; 

Should support dimension checking types etc by virtue of using fully generic intermediate values. 

Also includes various related functions:
   
   ```y = y0.lerp(&y1, t)```
   ```t=inv_lerp(&y,&y0,&y1)```     
   ```t.lerp_between(&y0,&y1)```,  
   ```t.lerp_points(&x0,&x1, &y0,&y1)``` , and 
   ```(y0,y1).lerp_by(t))```

where 't' is a dimensionless blending factor, x's and y's are types with potentially different dimensions. 

   ```y0.lerp(&y1,t).inv_lerp(&y0,&y1) == x```
   ```x.lerp_points(&x0,&x1, &y0,&y1) == y0.lerp(&y1,&x.inv_lerp(&x0,&x1)) ```

Uses reference args, anticipating use with non trivial types eg vectors, image arrays, etc.
However the factor is a simple value, anticipated to usually be f32

(also includes a helper 'pair_with()' for making tuples sequentially, e.g. ```x0.pair_with(&x1).lerp_by(t)```