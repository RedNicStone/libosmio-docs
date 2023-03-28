
libosmio's API design
=====================

This page was created to help new users understand how libosmio works.
It will give you a good idea of how the API works, as well as some insight in how API calls are resolved internally.

The design of the osmio ecosystem has been heavily inspired by the Vulkan graphics API at almost every place.
While knowledge of the Vulkan API may help you understand how osmio's API is structured, it is certainly not required.

Language compliance
-------------------

While libosmio's implementations are not restricted to a specific language, the API has been made compliant with C99.
Even though earlier iterations were designed for C++ specifically, C99 has been chosen for wider compiler support on embedded devices.

.. note::
    Whether you use C++, C or any other C-like language in your project, you will be able to use libosmio.

Library handles
---------------

Osmio uses opaque handles in many of its API functions.
These are to be treated like any other pointer, so you can copy and move them as much as you like.
Lifetime of a libosmio handle starts when it is created using a `osCreate...()` function and ends on `osDestroy...()`.

.. important::
    The raw data behind the handle is purposefully opaque as it is implementation-defined, so interfacing with it should be avoided outside of the library implementation.




