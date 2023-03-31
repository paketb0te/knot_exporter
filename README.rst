knot_exporter
=============

knot_exporter is a Prometheus exporter for `Knot DNS`_'s server and query statistics.

.. _`Knot DNS`: https://www.knot-dns.cz/

Getting Started
---------------

knot_exporter uses `Python libknot wrapper`_ to communicate with the Knot DNS
server via a control unix socket, so Knot has to be installed on the same
machine as knot_exporter, and knot_exporter must be executed by a user with
access to Knot's socket path.

.. _`Python libknot wrapper`: https://pypi.org/project/libknot/

The libknot wrapper, along with other required dependencies, can be installed from `requirements.txt` with pip (ideally in a virtual environment):

.. code-block:: bash

   $ pip install -r requirements.txt

The Knot instance also needs to be configured to collect per-zone query
statistic. This can be done by enabling and configuring the `stats module`_.

.. _`stats module`: https://www.knot-dns.cz/docs/latest/html/modules.html?highlight=mod%20stats#stats-query-statistics

Once everything is in place, knot_exporter can be started like so:

.. code-block:: bash

   $ ./knot_exporter.py

To get a complete list of the available options, run:

.. code-block:: bash

   $ ./knot_exporter.py --help

Copyright
---------

Copyright (C) 2018 Alessandro Ghedini <alessandro@ghedini.me>

Copyright (C) 2020 CZ.NIC, z.s.p.o. <knot-dns@labs.nic.cz>

See COPYING_ for the license.

.. _COPYING: https://github.com/ghedo/pflask/tree/master/COPYING
