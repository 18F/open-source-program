---
title: "Open Source Primer for Contracting Officers"
---


## Purpose

Open source software is a commercial product [under the Federal Acquisition Regulation (FAR)](https://www.acquisition.gov/sites/default/files/current/far/html/Subpart%202_1.html#wp1145508) and thus must be considered by COs during the acquisition process. The purpose of this primer is to familiarize Contracting Officers (COs) with open source software in order to aid in the acquisition process. 

## Definition

Open source software is software whose source code is freely available to be viewed, modified, and distributed by anyone. Source code is a set of instructions for a computer to complete. All software is expressed by its source code.

For example, the following is source code using the Python programming language:

```python
print(“Hello World”)
```

This source code, when run by a computer, displays the text “Hello World”. Although this example is trivial, the underlying concept applies to all software.

## Benefits

Using open source software allows the government to:

- Decrease costs;
- Avoid vendor lock-in;
- Maintain high standards of system quality.

Creating open source software allows the government to:

- Build [more reliable(http://ben.balter.com/open-source-for-government/#starting_an_open_source_project) software;
- Maintain flexibility;
- Incorporate feedback and code contributions from a community of users;
- Provide maximum value to the taxpayer.

## Background

The White House’s [Digital Government Strategy](https://www.whitehouse.gov/sites/default/files/omb/egov/digital-government/digital-government.html) described a “need to phase out the use of custom-built technology” and a recommendation that “the Federal Government use open source technology to enable more sharing of data and make content more accessible.”

Federal agencies are increasingly relying on the use and creation of open source software to achieve their IT objectives. By one estimate, there are [over 8,000](https://www.govcode.org/) open source software projects run by federal agencies. However, there is still plenty of room for federal agencies to increase their utilization and creation of open source software.

## The Open Source Software Ecosystem

Open source software is part of nearly all major software applications. If you are viewing this document using a web browser, it is highly likely that that web browser is open source software. If you are using a Mac computer, many of the core components of the operating system are open source. One of the most popular operating systems in the world, Linux, is entirely open source. Open source software has been around for decades and often meets or exceeds the quality and reliability of closed source counterparts.

To illustrate the reliability of open source software, a recent [Gartner report](https://www.gartner.com/doc/3033819/state-opensource-rdbmss-) found that open source database systems “can now [be] consider[ed] [] as a standard choice for deploying applications.”

Popular open source projects usually are run by a community of developers who rely on the software to meet their needs. Often, open source software is sponsored by a corporate backer. For example, Canonical Ltd. develops Ubuntu, an incredibly popular Linux-based operating system. Although Canonical is a for-profit corporation, Ubuntu is open source and thus is free to use, distribute, and modify. Anyone can submit a modification to Ubuntu, for example, and Canonical might incorporate that modification into the next version of the software.

## Using Open Source Software

When the government uses open source software for an IT project, the government benefits from the collective work, knowledge, and expertise that comes with the community around the open source software.

For example, if a defect is discovered in the Ubuntu operating system, it is highly likely that someone will develop a timely fix for the defect (also known as a “patch”). If a government IT system is using Ubuntu, government employees or contractors need not spend much time discovering defects in the operating and/or writing the fixes. This dynamic, where the government benefits from the collective action of a community of dedicated developers, can present significant cost savings and ensure high quality.

## Creating Open Source Software

When the government creates open source software (authored by government employees or contractors), the government benefits by ensuring flexibility, customizability, and re-use of the software. For example, a software component built by one agency to solve a problem might also solve a similar problem faced by other agencies. If the first agency released the component as open source software, the other agencies can re-use the component to meet their IT objectives. A real world example of such government-to-government re-use is a software program called [eRegulations](https://github.com/cfpb/eRegulations) (eRegs). eRegs is a tool that allows an agency to display on the web relevant sections from the Code of Federal Regulations. Originally written by developers at the Consumer Financial Protection Bureau (CFPB), eRegs has been used by several other agencies that have similar needs for their regulations.

## Licensing

According to the [Copyright Office](http://copyright.gov/circs/circ61.pdf), “Copyright protection extends to all the copyrightable expression embodied in the computer program.” Open source software is software whose license allows for its free use, modification, and distribution. The copyright-holder of software may also waive all associated rights and dedicate the work to the public domain. Such software is also considered to be open source.

Rather than draft a license each time an author releases their open source software, a software author can use one of an assortment of standard licenses. The website [choosealicense.com](http://choosealicense.com/) provides a glossary of the most common open source software licenses. Some of those licenses are:

- The [MIT License](https://opensource.org/licenses/MIT)
- The [Apache Licence](http://www.apache.org/licenses/LICENSE-2.0)
- The [GPL](http://www.gnu.org/licenses/gpl-3.0.en.html)

Works produced by the government (but not necessarily by government contractors) are automatically in the public domain. For government contracts, the contract should contain language requiring that all software developed under the contract be licensed using one of the common open source licenses.

Below is sample language to include in a contract to ensure that all software create is open source:

> The contractor shall develop all source code for software deliverables shall be made available by the contractor to the public as open source software, under the terms and conditions of a license determined or approved by [AGENCY].

> The subsystems will be built using non-proprietary, open-source software; all code developed as part of this contract which will be publically available on GitHub.

## Further Reading

- [Open Source for Government](http://ben.balter.com/open-source-for-government/)
- [Open Source Software in Government Acquisitions](http://www.dwheeler.com/essays/oss-government-acquisitions.html)
- [18F’s Open Source Policy](https://github.com/18F/open-source-policy/blob/master/policy.md)
- [18F Contracting Cookbook](https://pages.18f.gov/contracting-cookbook/)

