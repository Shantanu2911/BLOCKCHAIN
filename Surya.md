# Surya

1. **Contract Structure Information**:
    - Provides details about the contracts' structure.
    - Generates inheritance graphs.
    - Supports querying the function call graph.

2. **Visual Outputs**:
    - Outputs a **DOT-formatted graph** of the control flow.
    - Visualizes the relationships between functions and contracts.

3. **Manual Inspection Aid**:
    - Helps auditors understand and analyze Solidity smart contracts.
    - Useful for security assessments and vulnerability detection.


```
sudo apt install npm
```
```
sudo npm version
```


```
npm install -g surya
```
```
npm install -g surya
```
*if it's giving error then:-*
```
sudo su
```

```
npm install -g surya
```

```
apt install graphviz
```

*herw, you have to creat ur own file of .sol::--also you can go through with this given images:🔲*
![image](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/0bfc85fc-7e87-4191-be26-fd3118c0792f)


```
surya ftrace APMRegistry:: rajesh2.sol
surya ftrace <function_identifier> <function_visibility_restrictor> <files..>
```


```
surya parse rajesh2.sol
```
***after putting this command you will be get this interface***

*like a tree flow result:here as you ca see that:---*
![Screenshot from 2024-04-12 21-46-57](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/3de5e8f7-fe9d-494c-bf65-8a473184b7ef)

![Screenshot from 2024-04-12 21-47-07](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/0d27b06d-283d-4108-9a36-344ba5761009)
