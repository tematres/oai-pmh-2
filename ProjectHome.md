This is an implementation for an OAI-PMH 2.0 Data Provider (sometimes, repository is used exchangeablly) written in PHP.

This implementation completely complies to OAI-PMH 2.0, including the support of on-the-fly output compression which may significantly reduce the amount of data being transfered.

Database support is supported through PDO (PHP Data Objects included in the PHP distribution), so almost any popular SQL-database can be used without any changes in the code. The only thing needed to be done is to configure the database connection and define a suitable data structure.

This package has been inspired by PHP OAI Data Provider developed by Heinrich Stamerjohanns at University of Oldenburg. Some of the functions and algorithms used in this code were transplanted from his implementation at http://physnet.uni-oldenburg.de/oai/.

The goals were to:
  * implement of OAI-PMH with latest version of PHP and its modules.
  * support metadata format of RIF-CS for the in-house data capture project funded by [ANDS](http://www.ands.org.au).

The detail of implementation has been provided in doc folder in every release package.

The list of packages released as open source software:
  * ANDS data harvester and the data provider. [Source Code](http://code.google.com/p/oai-pmh-2/downloads/detail?name=oai-pmh-2.v1.1.zip&can=2&q=)
  * Database structure supporting ANDS data harvester. [Source Code](http://code.google.com/p/oai-pmh-2/downloads/detail?name=playground.backup&can=2&q=)
  * Web interface. [Source Code](http://code.google.com/p/oai-pmh-2/downloads/detail?name=APPF-PA-Project.zip&can=2&q=)