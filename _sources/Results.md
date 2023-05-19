# Results


According to the first Mortality plot, we could detect that the moratlity during 1988-2018 was higher when people self-reported their health as poor or bad. 


According to the second scatter plot, we observed that the self-reported health score was higher in the younger aged group in 2017-2018. 

```stata
set scheme s2color
nhanes
```

![](nh3andmort.png)

```stata
use merged1.dta, clear

#delimit ;
twoway 
    scatter  
	     health_s age_g , 
	         col(white) 
			 mcolor(%20) 
			 jitter(3) || 

	dot  
	     mean_health_s age_g, 
		 col(blue) 
		 msize(2)  
			legend(off ) 
			xlab(1 "10s" 
			     2 "20s" 
				 3 "30s" 
				 4 "40s" 
				 5 "50s"
				 6 "60s") 
		yline(90, lcol(red) lp(dash)) 
		xti("Age groups")
		yti("General Health Status")
		title("General Health Score by Age in 2017-2018 NHANES")
		ylabel(0(1)5);
#delimit cr
```

![](twoway_1.png)
