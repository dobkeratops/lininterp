generic linear interpolation; 

Should support dimension checking types ect by virtue of using fully generic intermediate values. 

Also includes various related functions:

   
   ```inv_lerp(x,x0,x1)```     
   ```f.lerp_between(y0,y1)```,  
   ```x.lerp_points(x0,x1,y0,y1)``` , and 
   ```(y0,y1).lerp_by(x))```


   ```y0.lerp(&y1,x).inv_lerp(&y0,&y1) == x```
   ```x.lerp_points(&x0,&x1, &y0,&y1) == y0.lerp(&y1,&x.inv_lerp(&x0,&x1)) ```

Uses reference args, anticipating use with non trivial types
However the factor is a simple value, anticipated to usually be f32