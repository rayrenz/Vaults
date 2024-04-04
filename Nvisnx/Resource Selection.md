`class SelectionAction`
```
{
	"target": str,
	"operation": [
		"select", 
		"unselect", 
		"select_all_subfolders", 
		"unselect_all_subfolders"
	],
	"search": "Optional[str]"
}
```

# Endpoints
- `POST /sources/{sourceId}/resources`
	- create resource
- `GET /sources/{sourceId}/resources`
	- lists resources with pagination

# Functions
- `_execute_all_actions`
	- `op_map` a list of executors for each action
- Operations:
	- "select_all_subfolders"
		- `ancestor_paths` 
		- `descendant_paths` 
		- `_reconcile_with_selected_paths`
- `apply_selection`
	- 