# mcce-develop
Current development version of mcce.

The task of this version of mcce is to consolidate the changes accumulated over the years since MCCE2 2009 paper.

## To install this development version

After downloading cloning this repository, go to the mcce directory, and run:

```
make clean
make
```

On Mac OS X, an explicit memory free for tree is not supported. You may have to change this subroutine in file lib/db.c
```C
/* release database memory */
void free_param() {
   tdestroy(param_root, free);
   return;
}
```
to
```C
/* release database memory */
void free_param() {
   return;
}
```

To test run the mcce code, refer [this page](https://sites.google.com/site/mccewiki/install-mcce)

## What is on the roadmap?
1. Step 4 writes out microstates only
  * achieve the most efficient sampling
  * write tools to do analysis
2. Analysis tools:
  * MC trajectory
  * Occupancy table
  * Titration curve fitting
  * Entropy correction
  * Interaction network and cluster identification
  * Cluster energy analysis
3. Chemical potential titration
  * add a column in head3.lst to titration chemical potential
4. Atom based VDW calculation
  * Use atom based parameters
  * separate from delphi calculation
5. Integrate delphi as function call   
