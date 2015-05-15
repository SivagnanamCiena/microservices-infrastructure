# HDFS

An Ansible role for installing [HDFS](https://hadoop.apache.org/docs/r1.0.4/cluster_setup.html)

## Variables

- `hdfs_version` - HDFS version (default: `2.6.0`)
- `hdfs_conf_dir` - Configuration directory for HDFS (default: `/etc/hadoop/conf`)
- `hdfs_install_dir` - Directory where to install HDFS (default: `/usr/local/share`)
- `hdfs_namenode_port` - Port of the HDFS name node (default: `8020`)
- `hdfs_hadoop_opts` - Extra Java runtime options for Hadoop (default: `-Djava.net.preferIPv4Stack=true`)
- `hdfs_properties` - A list of properties for `hdfs-site.xml` configuration file on the name node

## Example Playbook

    ---
    - hosts: name_node
      gather_facts: no
      roles:
        - {role: hdfs-standalone, hdfs_namenode: true}

    - hosts: data_nodes
      gather_facts: no
      roles:
        - {role: hdfs-standalone, hdfs_namenode: false}
