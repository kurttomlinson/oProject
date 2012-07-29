#oProject

A format for open source hardware project documentation. oProject is currently being developed for deployment on [Open Hardware Hub](http://www.openhardwarehub.com/). oProject is an open specification that will be developed based on community feedback. The goal of oProject is to provide a simple framework for documenting everything about an open source hardware project that is needed for replication of that project.

##Summary of Use

The only required file in an oProject is manifest.xml. It must be found in the root directory of the project. The manifest points to all the other xml files that describe the oProject in its entirety.

###Manifest File
The manifest file contains a root <project> element. Within the project element is a manifest element. The manifest element contains file elements with a url attribute that points to all of the oProject XML files for the project. In truth, all of the textual content of an oProject can be contained within the manifest.xml since all oProject files are validated with the same XML Schema Document, but this is not encouraged. Keeping all of the textual content in one file would reduce modularization and result in large, unwieldy xml files. For this reason, we recommend splitting your project into four oProject files: description.xml, downloads.xml, parts.xml, and steps.xml.

###Description file

###Downloads file

###Parts file

###Steps file

##Schema

The XML schema file for oProject can be found in the [Schemas](https://github.com/kurttomlinson/oProject/tree/master/Schemas) folder.

##Sample Project

There is a sample project complete with images in the [Documents](https://github.com/kurttomlinson/oProject/tree/master/Documents) folder that has been validated against the oProject.xsd schema.

##Documention

For documentation on the oProject.xsd schema, open index.html in the [Documentation](https://github.com/kurttomlinson/oProject/tree/master/Documentation) folder in your favorite web browser.
