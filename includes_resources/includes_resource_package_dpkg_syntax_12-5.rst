.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.


A |resource package_dpkg| resource block manages a package on a node, typically by installing it. The simplest use of the |resource package_dpkg| resource is:

.. code-block:: ruby

   dpkg_package 'package_name'

which will install the named package using all of the default options and the default action (``:install``).

The full syntax for all of the properties that are available to the |resource package_dpkg| resource is:

.. code-block:: ruby

   dpkg_package 'name' do
     notifies                   # see description
     options                    String
     package_name               String, Array # defaults to 'name' if not specified
     provider                   Chef::Provider::Package::Dpkg
     source                     String
     subscribes                 # see description
     timeout                    String, Integer
     version                    String, Array
     action                     Symbol # defaults to :install if not specified
   end

where 

* ``dpkg_package`` tells the |chef client| to manage a package
* ``'name'`` is the name of the package
* ``:action`` identifies which steps the |chef client| will take to bring the node into the desired state
* ``options``, ``package_name``, ``provider``, ``source``, ``timeout``, and ``version`` are properties of this resource, with the |ruby| type shown. |see attributes|
