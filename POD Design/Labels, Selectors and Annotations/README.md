# Labels, Selectors and Annotations
<h2><u>About</u></h2>
Annotations, labels, and selectors are used to manage metadata attached to your Kubernetes objects. Annotations and labels define the data while selectors provide a way to query it.
<br><br>
<h2><u>Labels</u></h2> 
Labels add propertties to a Pod<br>
For example if i added properties to my database:<br> - app = App1<br> - function = Database <br>
<br><br>
<h2><u>Selectors</u></h2>
Selectors help you filter the properties set with Labels
To target the DB example i used in Labels above i would use<br>
- function = Database<br>
<br>
This will return all containers Labeled with "Database"
<br>
The command to do this is<br>

`kubectl get pods --selector function=Database`

<br>
<h2><u>Example</u></h2>
In this directory there is a: <br>
- pod-definition.yaml <br>
- replicaset-definition.yaml <br>
- service-definition.yaml <br><br>
Each of these uses labels, and selctors("matchLabels") to demonstrate how labels and selectors are used in a real world scenario