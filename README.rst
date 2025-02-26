Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-htu31d/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/htu31d/en/latest/
    :alt: Documentation Status

.. image:: https://img.shields.io/discord/327254708534116352.svg
    :target: https://adafru.it/discord
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_HTU31D/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_HTU31D/actions
    :alt: Build Status

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black
    :alt: Code Style: Black

Python library for TE HTU31D temperature and humidity sensors


Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://circuitpython.org/libraries>`_.

Installing from PyPI
=====================

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-htu31d/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-htu31d

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-htu31d

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .env
    source .env/bin/activate
    pip3 install adafruit-circuitpython-htu31d

Usage Example
=============

.. code-block:: python

    import time
    import board
    import adafruit_htu31d

    i2c = board.I2C()  # uses board.SCL and board.SDA
    htu = adafruit_htu31d.HTU31D(i2c)
    print("Found HTU31D with serial number", hex(htu.serial_number))

    htu.heater = True
    print("Heater is on?", htu.heater)
    htu.heater = False
    print("Heater is on?", htu.heater)

    while True:
        temperature, relative_humidity = htu.measurements
        print("Temperature: %0.1f C" % temperature)
        print("Humidity: %0.1f %%" % relative_humidity)
        print("")
        time.sleep(1)

Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/htu31d/en/latest/>`_.

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_HTU31D/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.
