Envoy_3
======================================
Forked from `_kennethreitz/envoy <https://github.com/kennethreitz/envoy>`_

Since the Envoy package obtained from pip was actually different from that one on Github,
I pushed the pip-version code to this repository.


**Note:** `Delegator <https://github.com/kennethreitz/delegator.py>`_ is a replacement for Envoy.

This is a convenience wrapper around the `subprocess` module.

You don't need this.

.. image:: https://github.com/kennethreitz/envoy/raw/master/ext/in_action.png

But you want it.


Usage
-----

Run a command, get the response::

    >>> r = envoy.run('git config', data='data to pipe in', timeout=2)

    >>> r.status_code
    129
    >>> r.std_out
    'usage: git config [options]'
    >>> r.std_err
    ''

Pipe stuff around too::

    >>> r = envoy.run('uptime | pbcopy')

    >>> r.command
    'pbcopy'
    >>> r.status_code
    0

    >>> r.history
    [<Response 'uptime'>]
