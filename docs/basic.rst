Basic Logic, Wires, and Memories
================================

Wires define the relationship between logic blocks in PyRTL. They are treated like normal wires in traditional RTL systems except the :class:`.Register` wire.
Logic is then created when wires are combined with one another using the provided operators.  For example, if `a` and `b` are both of type `WireVector`,
the `a + b` will make an adder, plug `a` and `b` into the inputs of that adder, and return a new `WireVector` which is the output of that adder. 
Wires provide the basic input and output interfaces to the generated :class:`.Block` which stores the description of the hardware as you build it.

WireVector
----------

.. autoclass:: pyrtl.wire.WireVector
    :members:
    :show-inheritance:
    :special-members: __init__, __add__, __sub__, __mul__, __getitem___, __len__


Input, Output, Const, and Register
----------------------------------

The classes `Input`, `Output`, `Const`, and `Register` are all derived from WireVector, but
extend it with (or restrict it from) with certain functionality.  The `Input` and `Output`
classes are for those values that will be external to the entire system once complete (e.g.
driving a signal off-chip, rather than the interface to some particular sub-block of the 
design).  The `Const` class is useful for specifying hard-wired values, while `Register` is
how sequential elements are created (the all have an implict clock).

.. autoclass:: pyrtl.wire.Input
    :members:
    :show-inheritance:
    :special-members: __init__

.. autoclass:: pyrtl.wire.Output
    :members:
    :show-inheritance:
    :special-members: __init__

.. autoclass:: pyrtl.wire.Const
    :members:
    :show-inheritance:
    :special-members: __init__

.. autoclass:: pyrtl.wire.Register
    :members:
    :show-inheritance:
    :special-members: __init__


MemBlock
--------

.. autoclass:: pyrtl.memory.MemBlock
    :members:
    :show-inheritance:
    :special-members: __init__

RomBlock
--------

.. autoclass:: pyrtl.memory.RomBlock
    :members:
    :show-inheritance:
    :special-members: __init__
