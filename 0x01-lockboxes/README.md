Project description
lockbox: User-friendly CLI over cryptography.io's Fernet symmetric cipher
.. image:: https://img.shields.io/badge/python-2.6%202.7%203.3%203.4%203.5%203.6-blue.svg
:target: https://pypi.python.org/pypi/lockbox

.. image:: https://img.shields.io/badge/license-MIT-blue.svg
:target: https://pypi.python.org/pypi/lockbox

---------------

.. image:: https://s3.amazonaws.com/johnwheeler/lockbox.gif

**lockbox** provides a command line interface over cryptography.io's `Fernet symmetric cipher <https://cryptography.io/en/latest/fernet/>`_.
Fernet guarantees that a message encrypted using it cannot be manipulated or read without the key. lockbox was inspired by the Ruby-based
`sekrets <https://github.com/ahoward/sekrets>`_ project, but they use different ciphers.
