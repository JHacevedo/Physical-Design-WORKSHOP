# Physical-Design-WORKSHOP
# DAY 1
## Sky130 files:
Open source pdk SKY130A --> Compatible with our open source environment

![image](https://user-images.githubusercontent.com/100744116/183268944-43029356-e4f0-46db-9922-ba08413c745c.png)
> Fig. 1. PDK used

![image](https://user-images.githubusercontent.com/100744116/183269096-e2f2a30a-a1d5-4c0c-b06d-908bf0ca48b2.png)
> Fig. 2. libs

- libs.ref : Contains all related to the technology
- libs.tech : files related to the tool

## OpenLane

![image](https://user-images.githubusercontent.com/100744116/183269233-7f20ad46-fd67-477b-bcb4-b0e3153499ce.png)
> Fig. 3. File in which we are going to work

We have to do these three steps have to be done everytime we want to run OpenLane
+ Run "docker" command to create required environment.
+ Execute "./flow.tcl -interactive" to run the OpenLANE flow.
+ Import OpenLane package using "package require openlane"

![image](https://user-images.githubusercontent.com/100744116/183269415-5a4040eb-66fe-47d1-a8cd-0dbfe3dd9efc.png)
> Fig 4. Running OpenLane

### Design preparation step
**Command: prep -design picorv32a**

![image](https://user-images.githubusercontent.com/100744116/183269596-9a9b7ab4-ab17-4517-8859-657cd46b320a.png)
> Fig. 5. Running prep command

Once the preparatio is complete we run synthesis

**Command: Run_synthesis**

![image](https://user-images.githubusercontent.com/100744116/183273299-08208c99-b65f-4678-8e02-ece8681acb06.png)
> Fig. 6. Running Synthesis

![image](https://user-images.githubusercontent.com/100744116/183273404-e43d1fcd-40d4-4a61-90fa-094337b3f32f.png)


![image](https://user-images.githubusercontent.com/100744116/183273415-964c0618-59a0-4271-94a6-c7bbc0aa7e49.png)

![image](https://user-images.githubusercontent.com/100744116/183273476-f339f2ed-d2b3-4d78-b476-ecfe14c55212.png)


After running the synthesis we can see the total number of standard cells used in this particular design and the total area

Now we are asked to calculate the flop ratio of the d flip-flops(dfxtp_2), we calculate this ratio as follow --> Total # of flops  / Total # of cells

The total number of d flip-flops(dfxtp_2) is : 1634

And the total number of cells is : 14876

$$
FR = \frac{1634}{14876} = 0.1084 =>  10.84  \% 
$$

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%201.png)

Here we can check the shyntesis, all the mapping have been done

# Day 2

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%202.png)

## Floorplanning

After doing shynthesis what comes it’s the floorplant, where we set specific things in our design

Before that, we’ll see the global variables in our configuration

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%203.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%204.png)

We can set these variables (switches), right now they are place by default

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%205.png)

After we already check the variables for Floorplaning, synthesis etc… we run the command : run_floorplan

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%206.png)

We observe that the floorplan was successfully implemented.

We can calculate the area of the die at “picorv32a.floorplan.def”

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%207.png)

Running Magic

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%208.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%209.png)

Floorplanning in magic

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2010.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2011.png)

We check that the i/o pins are in the correspondent metal

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2012.png)

As we can see, the cells are unplaced, so we run a command to place them ‘’command : Run placement’’

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2013.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2014.png)

# Day 3

For this part, we have to clone vsdstdcelldesing from github 

```jsx
/home/Desktop/work/tools/openlane_working_dir/openlane
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
```

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2015.png)

Now we copy the [sky130A.tech](http://sky130A.tech) file into vsdstdcelldesign

```jsx
cp sky130A.tech /home/jherney30/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
```

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2016.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2017.png)

Sending to spice with parasitics

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2018.png)

To open .spice file use

```jsx
vim
```

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2019.png)

Modify the document

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2020.png)

And than, we run the simulation into ngspice

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2021.png)

After running the simulation, we plot our aoutput/inpit vs time

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2022.png)

# Day 4

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2023.png)

We observe the file associated to the tracks, these are using duranting the routing stage.

We ajust the spacing of the layout

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2024.png)

Generation of the .lef file

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2025.png)

We verify if everything is okay 

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2026.png)

![Untitled](Untitled%2076265fc49b49417596b202ad6effd888/Untitled%2027.png)

We see .lef file tha was generated



