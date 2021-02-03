{% include breadcrumbs.html %}


# Overview
`find_champions` is a function that filters a list of champions down to a subset that matches the provided arguments.

# Table of Contents
* auto-gen TOC:
{:toc}


# Arguments
`find_champions` takes in `name`, `role`, and `origin` arguments (all of type `string`).

# Dictionaries
`find_champions` uses a set of dictionaries, which contain a available list of champions with keys for their name, role, and origin. 

Here's an example of a dictionary with champions:
```
champion_data = [
 {
 'name': 'ahri',
 'role': 'mid lane',
 'origin': 'vastaya'
 },
 {
 'name': 'teemo',
 'role': 'top lane',
 'origin': 'bandle city'
 },
 {
 'name':'gangplank',
 'role': 'top lane',
 'origin': 'bilgewater'
 },
 {
 'name': 'sona',
 'role': 'support',
 'origin': 'ionia'
 },
 {
 'name': 'miss fortune',
 'role': 'marksman',
 'origin': 'bilgewater'
 }
]
```

# Behavior
* If `name` is specified and a Champion with that name exists, a single-element list is returned with that matching champion.
* If no match is found or no name is specified, and a `role` or `origin` have been specified, a list containing all champions whose `role` or `origin` match will be returned. 

# Code Sample

Here's an example of `find_champions` in action:
```
def find_champion(name=None, role=None, origin=None):
 champion_suggestions = []
 for champ in champion_data:
 	if name:
 		if champ['name'] == name:
 			return [champ]
	if role:
 		if champ['role'] != role:
 			continue
	if origin:
 		if champ['origin'] != origin:
 			continue
 	champion_suggestions.append(champ)
 return champion_suggestions
 
 champions = find_champion(name='sona')
 
 print(champions)
```

## Example Output
If you ran the above, you would see the following result:

```
[{'name': 'sona', 'role': 'support', 'origin': 'ionia'}]

```
