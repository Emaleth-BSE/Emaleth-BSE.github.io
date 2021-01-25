---
title: Dispatcher
layout: page
collection: gh-repos
permalink: /dispatcher/
---

Dispatcher is a godot singleton script which transforms a scene path or a scene name from pool into an object inside the tree, ready to be parented.


## Installation

1. Clone this repository and copy Dispatcher.gd into you project folder
2. Add Dispatcher.gd as autoload.


## Usage

```GDScript
Dispatcher.request("object_name_from_pool")
```
or
```GDScript
Dispatcher.request("scene_path")
```

## Contributing
Please open and issue with pseudocode / describe changes. 

## License
[MIT](https://choosealicense.com/licenses/mit/)
