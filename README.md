# Doubly Linked List + Git Simulator

This project implements a fully-featured **Doubly Linked List (DLL)** and a simplified **Git version-control simulator** built on top of it.  

## Doubly Linked List (DLL)

I implement a standard DLL supporting:
- `empty()` — O(1) check for whether the list is empty  
- `push(val, back)` — insert at front/back in O(1)  
- `pop(back)` — remove from front/back in O(1)  
- `list_to_dll(list)` — build a DLL from a Python list (O(n))  
- `dll_to_list()` — convert DLL → Python list (O(n))  
- `find(val)` — return first node with given value  
- `find_all(val)` — return all occurrences  
- `_find_nodes()` — required helper used by `find` / `find_all`  
- `remove(val)` — remove first matching value  
- `remove_all(val)` — remove all matching values  
- `_remove_node()` — required O(1) helper  
- `reverse()` — reverse the list in-place, adjusting pointers only  

All operations respect the required time/space constraints.

## Git Simulator

On top of DLL, I build a minimal Git system supporting:
- Creating commits (`commit(message)`)
- Moving backward/forward in commit history  
- Creating branches (`checkout_branch`)  
- Switching commits (`checkout_commit`)  
- Tracking the current branch & selected commit  
- Branching from any commit (but only one branch per commit)  

Each branch is built using a `GitBranch` class that **inherits from DLL**, storing commits as nodes.

## Required Classes

### `Node`
Basic DLL node storing:
- `value`
- `next`
- `prev`
- `children_branch` (for branching in the Git simulator)

### `DLL`
Implements the doubly linked list behavior (head, tail, size, etc).

### `GitBranch (DLL)`
Represents a branch timeline; supports:
- `push_commit()`
- `get_first_commit()`
- `get_last_commit()`

### `Git`
Core simulator that manages:
- `start` (main branch)
- `current_branch`
- `selected_commit`
- `visited_branches`
- movement + branching behavior

## Notes
- All complexity requirements must be met (30% of grade).  
- `_find_nodes` and `_remove_node` *must* be used by dependent methods.  
- No extra data structures (sets/dicts) allowed unless permitted.  
- Docstrings required for full credit.  
- Tests check both correctness and memory behavior.

## Project Structure
- `solution.py` — your implementation  
- `tests.py` — provided automated tests

