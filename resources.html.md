---
title: GitLab
---

# Resource requirements for GitLab for PCF
These are the default resource and IP requirements for installing the tile
<table border="1" class="nice">
	<tr>
		<th>Product</th>
		<th>Resource</th>
		<th>Instances</th>
		<th>CPU</th>
		<th>Ram</th>
		<th>Ephemeral</th>
		<th>Persistent</th>
		<th>Static IP</th>
		<th>Dynamic IP</th>
	</tr>
	<tr>
 		<td>GitLab</td>
	 	<td>file-server</td>
	 	<td>1</td>
		<td>2</td>
	 	<td>8162</td>
		<td>1,024,000</td>
	 	<td>0</td>
	 	<td>1</td>
	 	<td>0</td>
 	</tr>
 	<tr>
 		<td>GitLab</td>
 		<td>gitlab-ee</td>
 		<td>2</td>
 		<td>2</td>
 		<td>2048</td>
 		<td>10240</td>
 		<td>0</td>
 		<td>1</td>
 		<td>0</td>
 	</tr>
</table>

#### Notes:
* The `file-server` instance count cannot be increased
* The `gitlab-ee` instance count can be increased to scale out horizontally

The amount of `gitlab-ee` instances depends on your usage pattern. 
We recommend by starting with two instances for teams up to 100 people. 
Please contact GitLab support if in doubt.
