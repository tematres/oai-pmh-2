# Introduction #

This is an implementation for an OAI-PMH 2.0 Data Provider (sometimes, repository is used exchangeablly) written in PHP.

This implementation completely complies to OAI-PMH 2.0, including the support of on-the-fly output compression which may significantly reduce the amount of data being transfered.

This package has been inspired by PHP OAI Data Provider developed by Heinrich Stamerjohanns at University of Oldenburg. Some of the functions and algorithms used in this code were transplanted from his implementation at http://physnet.uni-oldenburg.de/oai/.

Database support is supported through PDO (PHP Data Objects included in the PHP distribution), so almost any popular SQL-database can be used without any change in the code. Only thing need to do is to configure database connection and define a suitable data structure.

The repository can be quite easily configured by just editing oaidp-config.php, most possible values and options are explained.


# Requirements #

A running web server + PHP version 5.0 or above.
A databse can be connected by PDO.

# Installation #
Copy the the files in source package to a location under your document root of your web server. The directory structure should be preserved.
Change to that directory (e.g. cd /var/www/html/oai).
Allow your webserver to write to the token directory. The default token directory is /tmp which does not need any attention.
Edit oaidp-config.php. Almost all possible options are explained. It is assumed that basic elements of a record are stored in one simple table. You can find sql examples of table definition in doc folder. If your data is organized differently, you have to adjust the Query functions to reflect it and even develop your own code.
Check your oai site through a web browser. e.g. :
> http://localhost/oai/
SELinux needs special treatments for database connection and other permission.


# Structure #

The system includes files for individual functionality and utility classes and functions to get it work.
Controller

oai2.php

Individual functionalities:

identify.php: identifies the data provider. Responses to Identify.

listmetadataformats.php: lists supported metadata formats, e.g. dc or rif-cs. Responses to ListMetadataFormats.

listsets.php: lists supported sets, e.g. Activity, Collection or Party. Responses to ListSets.

listrecords.php: lists a group of records without details. Responses to ListRecords. It also serves to ListIdentifiers which only returns identifiers.
getrecord.php: gets an individual record. Responses to GetRecord.

Utility classes

xml\_creater.php which includes classess ANDS\_XML, ANDS\_Error\_XML, ANDS\_Response\_XML

Utility functions

oaidp-util.php

Support to different metadataformats in your own systems. Two examples provided with the package are: record\_dc.php and record\_rif.php. They are helpers and need information from the real records. They need to be devloped for your particular system.

Configurations

oaidp-config.php