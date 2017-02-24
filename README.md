# Presto Sqlserver Plugin

This is a plugin for Presto that allow you to use Sqlserver Jdbc Connection

The code is mainly inherited from [lotuc/presto-oracle](https://github.com/lotuc/presto-oracle) which is forked from [marcelopaesrech/presto-oracle](https://github.com/marcelopaesrech/presto-oracle)

## Connection Configuration

Create new properties file inside etc/catalog dir:

    connector.name=sqlserver
    connection-url=jdbc:sqlserver://ip:port/database
    connection-user=
    connection-password=

## Building Presto Oracle JDBC Plugin

    gradle build

## Plugin installation

First build the plugin.

Then create a dir inside plugin dir called sqlserver. To make it easier you could copy mysql dir to sqlserver and remove the mysql-connector and prestodb-mysql jars. Finally put the prestodb-sqlserver in plugin/sqlserver folder. Here is the sptes:

    cd $PRESTODB_HOME
    cp -r plugin/mysql plugin/sqlserver
    rm plugin/sqlserver/mysql-connector*
    rm plugin/sqlserver/presto-mysql*
    cp $SQLSERVER_PLUGIN_REPO/lib/* plugin/sqlserver
    cp $SQLSERVER_PLUGIN_REPO/build/libs/presto-sqlserver*.jar plugin/sqlserver

