# Better ABC

https://stackoverflow.com/questions/23831510/abstract-attribute-not-property

## Usage 

```python
from better_abc import ABCMeta, abstract_attribute    # see below

class AbstractFoo(metaclass=ABCMeta):

    @abstract_attribute
    def bar(self):
        pass

class Foo(AbstractFoo):
    def __init__(self):
        self.bar = 3

class BadFoo(AbstractFoo):
    def __init__(self):
        pass
```

```
Foo()     # ok
BadFoo()  # will raise: NotImplementedError: Can't instantiate abstract class BadFoo
# with abstract attributes: bar
```

If you want other features of ABC they need to be imported from the abc module directly.

```python
from abc import abstractmethod
from better_abc import ABCMeta, abstract_attribute
```