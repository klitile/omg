Software Requirements Specification for OMG Version 0.8
=======================================================

.. toctree::
    :maxdepth: 2
    :numbered:

    introduction
    functional-requirements
    non-functional-requirements
    constraints
    change-cases
    milestones
    appendices
    references
    
Group Information
=================

Group Member:
--------------
王雪洁(201732120106) 249795581@qq.com
 
Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

Introduction
============
This document is a specification for the omg project, omg for my genes, a web application for biologists to upload gene expression files and quickly show gene expression differences.

Purpose
-------
Identify differences in gene expression in gene expression files containing two gene samples.

Overview
--------
The web app has a simple page with an upload file and two buttons to execute, and the biologist uploads a plain text file with two sample gene expression levels. After receiving the instruction, the software will return a gene scatter diagram with x axis as control and y axis as knock out, and when the mouse points, the gene id will be displayed.

User characteristics
--------------------
* clients: Biologists who are using the web to get result of gene expression.
* maintainer: a computer scientist with knowledge of python and github.

Terminology&Glossary
--------------------

Terminology
~~~~~~~~~~~
* Control sample - a sample of a cell gene prepared under normal conditions.
* Knockout sample - a sample of a cell's genes that has been chemically altered to allow the gene to be altered.
* Differentially expressed genes - genes with markedly different levels of gene expression between two samples.
* Up-regulation - a gene is considered up-regulated if it is more expressed during treatment than in the control group.
* Down-regulation - a gene is considered down-regulated if it is less expressed during treatment than in the control group.

Glossary
~~~~~~~~
* logFC - log fold change of gene expression. 
* log_2 [T/C], where T is the gene expression level from a knock out sample, while C is the gene expression level from a control sample.

Functional requirements
=======================

Input
-----
A valid submitted gene expression file has the following format. It is a TAB- delimited.This 
file has a header file, including gene id, control sample, output sample, a total of three 
lines.
See the txt file pattern as following:

    ===========  =================  =================
      gene_id      ControlSample      KnockOutSample
    ===========  =================  =================
     AT1G01010      1.198558083        2.036161827
     AT1G01020      13.75736234        13.370796 
     AT1G01030      0.833779536        0.203616183 
     AT1G01040      9.58846466         7.126566394 
     AT1G01046      0                  0 
     AT1G01050      23.81482799        21.10821094 
     AT1G01060      0.625334652        1.221697096 
     AT1G01070      1.719670292        0.950208853 
     AT1G01080      28.34850421        25.24840665 
     AT1G01090      58.26034505        42.96301455 
     AT1G01100      1066.508249        1308.030358 
     AT1G01110      2.709783491        1.425313279
    ===========  =================  =================

Output
------
The web application displays a table and a scatter plot of the gene expression.The table contains differences in the expression of a group of genes with the following format:

    ===========  =================  =================  =============
      gene_id      control_sample    knockout_sample     log_2[FC]
    ===========  =================  =================  =============
     AT1G01020	   13.75736234	      13.370796           -0.04
    ===========  =================  =================  =============

The scatter plot displays differentially expressed genes. The X-axis is ControlSample, and Y-axis is KnockOutSample. The up-regulated genes are shown above the slash, and down-regulated genes are shown below the slash.

.. image:: https://raw.githubusercontent.com/klitile/omg/master/oh_my_gene/source/omg.png 

Non-functional Requirements
============================

Response Time
--------------
Because this web application is being used by biologists around the world, servers can become overloaded. If the user has a large amount of data, time complexity must be considered. Overall, the response time should be less than five seconds.

Aesthetic Aspects
-----------------
The page should be easy to understand.
the results should be clear.

Confidentiality Policy
----------------------
For biologists, every result of data is precious, so it is crucial to protect the safety of genetic information. Our network program must ensure the correct reliability of data, security and confidentiality. The experimental data and results cannot be disclosed privately.

Constraints
===========
This application is aimed at biologists around the world. Before development, we need to consider some constraints, such as how to solve the network congestion problem that many people use at the same time, etc. With the development of technology, these constraints will be solved, and then new constraints will be generated.

Compatibility
-------------
Because the application is used worldwide, it should be cross-platform compatible and accessible through most browsers, such as Firefox.

Servet space
------------
Web space less than 1GB.

Budget
------
Budget less than 10,000 dollors.

System downtime
---------------
System downtime less than 30 minutes per year.

Change cases
============
With the progress of information technology and genetics, there are some potential problems we may need to consider, they are divided into two aspects for us to talk about in following two things.

Information technology aspects
------------------------------
Information technology is developing very fast .No matter how it changes, the basic framework is the same. As the gene pool data increases, we need to optimize the gene pool, shorten the response time of the browser.

Genetics aspects
----------------
The future of genetics is uncertain, but it is certain that the gene pool will become larger and larger, and we must learn to organize and plan the gene pool.

Milestones
==========
1.Submit SRS for review by March 27th.

2.Get design done by April 3rd.

3.Get coding done by May 1st.

4.Acceptance tests by May 15st.

5.Release by June 5th.

(This is tentative.)

Appendices
==========
From March 10th to March 27th,I do some plans in flowing:

1.Understand the purpose and direction of the application.

2.Understand the requirements of omg software.

3.How to realize the generation of scatter diagram and how to move the mouse over the point to show the gene id.

4.Decided the project developing milestones.

References
==========
OMG's example of ReadTheDocs:
https://oh-my-gene.readthedocs.io/en/latest/





