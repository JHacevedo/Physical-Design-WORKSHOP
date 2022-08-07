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



# DAY 2
# DAY 3
# DAY 4
# DAY 5
