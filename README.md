# Simulations mito-nuclear discordance and sex-biased dispersal correlation in SLiM
Codes that have been used to test the correlation between mito-nuclear discordance and sex-biased dispersal using SLiM

To run the simulations we used the following scripts:

NBD:
```
slim -d seed=$seed -d Sm=0.5 -d Sf=0.5 -d K=50000 SCRIPT_MITONUCLEAR.slim > "$seed"_NBD_out
```
FBD:
```
slim -d seed=$seed -d Sm=0.5 -d Sf=1 -d K=50000 SCRIPT_MITONUCLEAR.slim > "$seed"_FBDFMM_out
```

MBD:
```
slim -d seed=$seed -d Sm=1 -d Sf=0.5 -d K=50000 SCRIPT_MITONUCLEAR.slim > "$seed"_MBDMMM_out
```

We ran ten replicas of each model with the following command
```
for i in {1..10};do qsub -v seed=$i NBD.sh ;done
```
