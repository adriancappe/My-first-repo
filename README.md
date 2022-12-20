# Test file

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```


```plantuml

skinparam monochrome false
skinparam defaultFontName Helvetica Neue
skinparam roundcorner 20
skinparam linetype polyline
caption **Figure 1:** Mapping between components and an agnostic Topology Structure

actor "RAN Operator" as RANOp


'RAN MAnagement Block
node "Solution A" as RANMgmt {
      
  [Component-01] --down->[Component-02]  
}

'TCM MAnagement Block
node "Automation Framework" as TCMMgmt {

interface "API Interface" as APIIF 
node "API Interface" as APIINTF {  
  [API_Intf_1]
  [API_Intf_2]
}

node "Database" as DB {  
  [Leaf-Type1] --down->[Leaf-Type2]

}
node "Ansible/Python Lirary" as APL {

[Wrapper01]
[Wrapper02]

}

} 

[Component-01].......right.......>[Leaf-Type1]: Mapping between components
[Component-02].......right.......>[Leaf-Type2]

[Leaf-Type1] ..>[Wrapper01] #blue;line.dashed :Task Execution 
[Leaf-Type2] ..> [Wrapper02] #blue: Task Execution
[Wrapper01] ..left.>[Component-01] #green;line.dotted : Action of the wrappers \nto the components 
[Wrapper02] ..left.>[Component-02] #green;line.dotted  :Action of the wrappers \nto the components 
 APIIF -down-- APIINTF
 [API_Intf_1] --left-> [Leaf-Type1]
 [API_Intf_2] --left-> [Leaf-Type2]


```
