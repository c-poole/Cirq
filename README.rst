.. image:: https://raw.githubusercontent.com/quantumlib/Cirq/master/docs/Cirq_logo_color.png
  :target: https://github.com/quantumlib/cirq
  :alt: Cirq
  :width: 500px

Cirq is a Python library for writing, manipulating, and optimizing quantum
circuits and running them against quantum computers and simulators.

.. image:: https://travis-ci.com/quantumlib/Cirq.svg?token=7FwHBHqoxBzvgH51kThw&branch=master
  :target: https://travis-ci.com/quantumlib/Cirq
  :alt: Build Status

.. image:: https://badge.fury.io/py/cirq.svg
    :target: https://badge.fury.io/py/cirq

.. image:: https://readthedocs.org/projects/cirq/badge/?version=latest
    :target: https://readthedocs.org/projects/cirq/versions/
    :alt: Documentation Status

Installation
------------

Follow these
`instructions <https://cirq.readthedocs.io/en/stable/install.html>`__.

Hello Qubit
-----------

A simple example to get you up and running:

.. code-block:: python

  import cirq

  # Pick a qubit.
  qubit = cirq.GridQubit(0, 0)

  # Create a circuit
  circuit = cirq.Circuit(
      cirq.X(qubit)**0.5,  # Square root of NOT.
      cirq.measure(qubit, key='m')  # Measurement.
  )
  print("Circuit:")
  print(circuit)

  # Simulate the circuit several times.
  simulator = cirq.Simulator()
  result = simulator.run(circuit, repetitions=20)
  print("Results:")
  print(result)

Example output:

.. code-block:: bash

  Circuit:
  (0, 0): ───X^0.5───M('m')───
  Results:
  m=11000111111011001000


Documentation
-------------

See
`here <https://cirq.readthedocs.io/en/stable/>`__
or jump into the
`tutorial <https://cirq.readthedocs.io/en/stable/tutorial.html>`__.

Contributing
------------

We welcome contributions. Please follow these
`guidelines <https://github.com/quantumlib/cirq/blob/master/CONTRIBUTING.md>`__.

We use
`Github issues <https://github.com/quantumlib/Cirq/issues>`__
for tracking requests and bugs. Please post questions to the
`Quantum Computing Stack Exchange <https://quantumcomputing.stackexchange.com/>`__ with the
`cirq <https://quantumcomputing.stackexchange.com/questions/tagged/cirq>`__ tag.
For informal discussions about Cirq, join our `cirqdev <https://gitter.im/cirqdev>`__ Gitter channel.

See Also
--------

For those interested in using quantum computers to solve problems in
chemistry and materials science, we encourage exploring
`OpenFermion <https://github.com/quantumlib/openfermion>`__ and
its sister library for compiling quantum simulation algorithms in Cirq,
`OpenFermion-Cirq <https://github.com/quantumlib/openfermion-cirq>`__.

Alpha Disclaimer
----------------

**Cirq is currently in alpha.**
We are still making breaking changes.
We *will* break your code when we make new releases.
We recommend that you target a specific version of Cirq, and periodically bump to the latest release.
That way you have control over when a breaking change affects you.

Cirq is not an official Google product. Copyright 2018 The Cirq Developers
