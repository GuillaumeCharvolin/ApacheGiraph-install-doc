Installation Guide for Apache Giraph
====================================

This guide describes the steps to install Apache Giraph on Ubuntu 24.04.1 LTS.

Prerequisites
=============

- Java 8
- Hadoop 2.x

Download and Install Giraph
===========================

1. **Download Giraph**:

   Obtain Giraph from the official Apache website:

   `https://archive.apache.org/dist/giraph/giraph-1.3.0/giraph-dist-1.3.0-hadoop2-bin.tar.gz``

2. **Extract the Archive**:

   .. code-block:: bash

      tar -xzf giraph-dist-1.3.0-hadoop2-bin.tar.gz
      sudo mv giraph-1.3.0-hadoop2-for-hadoop-2.5.1 /opt/giraph

3. **Set Environment Variables**:

   Add the following lines to your `~/.bashrc`:

   .. code-block:: bash

      # Giraph
      export GIRAPH_HOME="/opt/giraph"
      export PATH="$GIRAPH_HOME/bin:$PATH"

   Reload the `~/.bashrc`:

   .. code-block:: bash

      source ~/.bashrc

Configure Giraph
================

1. **Edit `giraph-site.xml`**:

   Configure Giraph by editing the `giraph-site.xml` file located in `$GIRAPH_HOME/conf`.

   Example configuration:

   .. code-block:: xml

      <?xml version="1.0"?>
      <configuration>
         <property>
            <name>giraph.jobGraphFile</name>
            <value>graph</value>
         </property>
         <property>
            <name>giraph.zkServers</name>
            <value>localhost:2181</value>
         </property>
      </configuration>
      
2. **Check Giraph Logs**:

   Monitor the logs for job status and issues. Logs are usually found in `$GIRAPH_HOME/logs`.

Uninstall Giraph
================

To uninstall Giraph, simply remove the Giraph directory:

.. code-block:: bash

   sudo rm -rf /opt/giraph
