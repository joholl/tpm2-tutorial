.. SPDX-License-Identifier: BSD-2-Clause

Hello World!
============

Let's start hacking! Sinve nowadays, every modern laptop and PC has a TPM 2.0.
I'll assume there is one on your machine, as well. On GNU/Linux systems, the TPM
can be accessed via two character devices.


.. code-block:: bash

    $ ls /dev/tpm*
    /dev/tpm0  /dev/tpmrm0


If you are on Windows, TODO.

Of course you might not want to use your TPM for development. In this case,
you can either use a TPM simulator or a Raspberry Pi. TODO

Installation
------------

Install the TPM Software Stack. If you're using Ubuntu, you can type the
following. If you're using another GNU/Linux distribution, you can look up the
package name at `repology.org/project/tpm2-tss
<https://repology.org/project/tpm2-tss/versions/>`_.

.. code-block:: bash

    $ sudo apt install tpm2-tss

.. note::

    You need version 2.4.0 or higher, 3.x if possible. If there is no such
    package available for your system, you need to build from source. (Don't
    fret, it's easy!) TODO





There are great tools ready to use, helping you with the most common tasks.
Again, for distributions which do not use `apt`, you'll find the package name at
`repology.org/project/tpm2-tools <https://repology.org/project/tpm2-tools/versions/>`_.

.. code-block:: bash

    $ sudo apt install tpm2-tools

.. note::

    You need version 4.2 or higher, 5.x if possible. Again, if your package
    manager does only provide outdated version, you need to build from source.
    TODO

Provision your System
---------------------

If you're using the TSS Feature API for the first time, you need to provision
your system. Don't worry, that's easy.

.. code-block:: bash

    $ tss2_provision

Yes, that's it. That call sets up the directories for your key store, log files
etc. If your system is provisioned already, the tool will tell you and abort.

List the TPM Keys
-----------------

There are some (special) keys in the key store already. You can simply lisz them
by calling the `tss2_list` tool.

.. code-block:: bash

    $ tss2_list
