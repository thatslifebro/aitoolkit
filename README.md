# AI Toolkit

<center>

![tests](https://img.shields.io/github/actions/workflow/status/linkdd/aitoolkit/tests.yml?style=flat-square&logo=github&label=tests)
![docs](https://img.shields.io/github/actions/workflow/status/linkdd/aitoolkit/docs.yml?style=flat-square&logo=github&label=docs)
![license](https://img.shields.io/github/license/linkdd/aitoolkit?style=flat-square&color=blue)
![version](https://img.shields.io/github/v/release/linkdd/aitoolkit?style=flat-square&color=red)

</center>

**AI Toolkit** is a header-only C++ library which provides tools for building
the brain of your game's NPCs.

It provides:

 - Finite State Machines
 - Behavior Tree
 - Utility AI
 - Goal Oriented Action Planning

## Installation

Add the `include` folder of this repository to your include paths.

Or add it as a submodule:

```
$ git submodule add https://github.com/linkdd/aitoolkit.git
$ g++ -std=c++23 -Iaiotoolkit/include main.cpp -o mygame
```

## Usage

### Finite State Machine

TODO

### Behavior Tree

Include the header:

```cpp
#include <aitoolkit/behtree.hpp>

using namespace aitoolkit::bt;
```

Create your blackboard type:

```cpp
struct blackboard_type {
  // ...
};
```

Create your tree:

```cpp
auto tree = seq<blackboard_type>::make({
  check<blackboard_type>::make([](const blackboard_type& bb) {
    // check some condition
    return true;
  }),
  task<blackboard_type>::make([](blackboard_type& bb) {
    // perform some action
    return execution_state::success;
  })
});
```

Evaluate it:

```cpp
auto blackboard = blackboard_type{
  // ...
};

auto state = tree->evaluate(blackboard);
```

For more informations, consult the
[documentation](https://linkdd.github.io/aitoolkit/group__behtree.html).

### Utility AI

TODO

### Goal Oriented Action Planning

TODO

## Documentation

The documentation is available online [here](https://linkdd.github.io/aitoolkit).

You can build it locally using [doxygen](https://www.doxygen.nl/):

```
$ make docs
```

## License

This library is released under the terms of the [MIT License](./LICENSE.txt).
