.. _quickstart:

Quickstart
==========

Starting the Server
-------------------

Open the Skill console in Virtuoso and type

.. code-block:: lisp

    load("PATH-TO-SKILL-IPC-SCRIPT")
    pyStartServer

You can obtain the correct path from the python library like this:

.. code-block:: sh

    skillbridge path


Read more about :ref:`server`.

One-time setup
--------------

Before you can use the python library you must generate the list of function
available in Skill. Type this once into the Skill console,
after you loaded the Skill script.

.. code-block:: lisp

    pyDumpFunctionDefinitions "<install>"

After that you can generate the static completion stub file. That is useful
for IDEs like PyCharm. Type this once into a terminal after you generated the
function definitions.

.. code-block:: sh

    skillbridge generate


.. note::

    Generating the static completion stub files requires a tool called ``stubgen``.
    You can install it alongside the python static type check ``mypy`` by typing
    ``pip install mypy`` into your shell.


If you have another working installation of the ``skillbridge`` you can export its definitions
and import them into your new installation

.. code-block:: sh

    # in the old environment
    skillbridge export /absolute/path/to/temporary/file.txt

    # in the new environment
    skillbridge import /absolute/path/to/temporary/file.txt


Connecting to the Server
------------------------


.. code-block:: python

    from skillbridge import Workspace

    ws = Workspace.open()

Here are some :ref:`basic`.