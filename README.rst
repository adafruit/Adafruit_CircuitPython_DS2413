
Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-ds2413/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/ds2413/en/latest/
    :alt: Documentation Status

.. image:: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Bundle/main/badges/adafruit_discord.svg
    :target: https://adafru.it/discord
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_DS2413/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_DS2413/actions/
    :alt: Build Status

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black
    :alt: Code Style: Black

CircuitPython driver for the DS2413 one wire 2 channel GPIO breakout.

Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Adafruit OneWire <https://github.com/adafruit/Adafruit_CircuitPython_OneWire>`_

**Note:** This library depends on the OneWire library and will **not** work on the Raspberry Pi

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Installing from PyPI
====================

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-ds2413/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-ds2413

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-ds2413

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .venv
    source .venv/bin/activate
    pip3 install adafruit-circuitpython-ds2413

Usage Example
=============

.. code-block:: python

    import time
    import board
    from adafruit_onewire.bus import OneWireBus
    import adafruit_ds2413

    ow_bus = OneWireBus(board.D2)
    ds = adafruit_ds2413.DS2413(ow_bus, ow_bus.scan()[0])

    led = ds.IOA
    button = ds.IOB
    button.direction = adafruit_ds2413.INPUT

    while not button.value:
        led.value = True
        time.sleep(0.5)
        led.value = False
        time.sleep(0.5)


Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/ds2413/en/latest/>`_.

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_DS2413/blob/main/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.
