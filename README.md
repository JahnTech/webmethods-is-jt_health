# JT_Health package for webMethods Integration Server 

The job of the JT_Health package for Integration Server
is to look at various settings and status values. This
allows you to get an understanding whether or not the server
is in good shape.

## How It Works

The package provides its functionality via services. Those
are exposed as REST resources, but can also be called from
other packages. The latter makes it possible to build additional
functionality to support more specialized requirements.


## Installation

Download the latest release ZIP
[from here](https://github.com/JahnTech/webmethods-is-jt_health/releases)
and install like any other package.

## Usage

You can use the provided REST resources to integrate with your
monitoring system of choice. The latter could also be Kubernetes,
if you want to know how your container node is doing.

## Security

No particular security configuration is in place right now. So
you will need an account with Administrator privileges to use
the services.

## Services

The table below contains an overview of the available functionality.

| Funtionality | REST | Underlying service |
|--------------| ---- | ------------------ |
| All adapter connections |  `/adapterConnections` | `jt.health.pub.is.art:getAdapterConnections` |
| Specific adapter connection |  `/adapterConnections/<CONNECTION_ALIAS>` | `jt.health.pub.is.art:getAdapterConnectionByAlias` |

As usual the REST resources need to be called with `/restv2` prepended. So if you
want to see all of the ART adapter connections on your local system,
you would use `GET http://localhost:5555/restv2/adapterConnections`.


______________________
This tool is provided as-is and without warranty or support. Users are free
to use, fork and modify it, subject to the license agreement.
While JahnTech GmbH welcomes contributions, we cannot guarantee
to include every contribution in the master project.

Contact us at [JahnTech](mailto:info@jahntech.com?subject=Github/JT_Health)
if you have any questions.

webMethods® is a registered trademark of International Business Machines Corporation (“IBM”).
