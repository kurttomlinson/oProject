#oProject

A format for open source hardware project documentation. oProject is currently being developed for deployment on [Open Hardware Hub](http://www.openhardwarehub.com/). oProject is an open specification that will be developed based on community feedback. The goal of oProject is to provide a simple framework for documenting everything about an open source hardware project that is needed for replication of that project.

##Summary of Use

The only required file in an oProject is manifest.xml. It must be found in the root directory of the project. The manifest points to all the other xml files that describe the oProject in its entirety.

###Manifest File
The manifest file contains a root <project> element. Within the project element is a manifest element. The manifest element contains file elements with a url attribute that points to all of the oProject XML files for the project. In truth, all of the textual content of an oProject can be contained within the manifest.xml since all oProject files are validated with the same XML Schema Document, but this is not encouraged. Keeping all of the textual content in one file would reduce modularization and result in large, unwieldy xml files. For this reason, we recommend splitting your project into four oProject files: description.xml, downloads.xml, parts.xml, and steps.xml.

###Description file
The description file should hold general information about the project itself.

*	name - Content: The name of your project. Attributes: None.
*	author - Content: The name of the person/group responsible for the project. Attributes: None.
*	images - Content: None. Attributes: None.
	*	image - Content: None. Attributes: "url" is a relative path to the image. "order" determines the order in which the images are shown. Images are shown in ascending order starting with 1.
		*	description - Content: A description of the image. Attributes: None.
*	video - Content: None. Attributes: "url" is an absolute path to a YouTube video of the project. (Other services may be allowed depending on the project hosting platform.)
*	description - Content: An HTML-formatted description of your project. Attributes: None.
*	license - Content: None. Attributes: "url" is a relative path to the license file.
	*	name - Content: The name of the license under which your project is licensed. Attributes: None.

###Downloads file
The downloads file should those files which are necessary to reproduce your project (such as compiled binaries, GERBER files, and other files that are in a final and usable form. Source code, schematics, and board files should be included in the project directory but not highlighted by the downloads folder. These files are the bare minimum needed to build your project in a production environment.

*	files - Content: None. Attributes: None.
	*	file - Content: A descriptive name for the file. Attributes: "url" is a relative path to the file. "order" determines the order in which the download files are shown. Download files are shown in ascending order starting with 1.

###Parts file
The parts file is a bill of materials along with links to suppliers. This makes it easy for consumers of your open source project to source their own parts to reproduce your project.

*	parts - Content: None. Attributes: None.
	*	part - Content: None. Attributes: "url" is an absolute path to a supplier's page for the part. "order" determines the order in which the parts are shown. Parts are shown in ascending order starting with 1.
		*	SKU - Content: The part's manufacturer's part number. Attributes: None.
		*	description - Content: A description of the part (value, ratings, package type, etc.) Attributes: None.
		*	quantity - Content: How many of this particular part are needed. Attributes: None.
		*	external\_reference - Content: None. Attributes: None.
			*	external\_id - Content: The unique id used to identify the part at the external\_source. Attributes: None.
			*	external\_source - Content: The external source that is used to provide an easy means to quickly acquire the part. Acceptable sources are currently limitied to Digi-Key and Octopart. Attributes: None.
		*	schematic_id - Content: The identification tokens (such as R1, C1, Q1, etc.) that identify this part in the schematic. This list should be comma delimited and/or use hypens to indicate a range of values (e.g. "R1,R2", "C3-5", or "Q1, Q6-9"). Attributes: None
		*	image - Content: None. Attributes: "url" is a relative path to the image.

###Steps file
The steps file gives step-by-step instructions for building the project from the parts listed in the parts file and using the files highlighted by the downloads file.

*	steps - Content: None. Attributes: None.
	*	step - Content: None. Attributes: "order" determines the order in which the steps are shown. Steps are shown in ascending order starting with 1.
		*	title - Content: A title for the step. Attributes: None.
		*	description - Content: A detailed, HTML-formatted explanation of how to execute the step. Attributes: None.
		*	images - Content: None. Attributes: None.
			*	image - Content: None. Attributes: "url" is a relative path to the image. "order" determines the order in which the images are shown. Images are shown in ascending order starting with 1.

##Schema

The XML schema file for oProject can be found in the [Schemas](https://github.com/kurttomlinson/oProject/tree/master/Schemas) folder.

##Sample Project

There is a sample project complete with images in the [Documents](https://github.com/kurttomlinson/oProject/tree/master/Documents) folder that has been validated against the oProject.xsd schema.

##Documention

For documentation on the oProject.xsd schema, open index.html in the [Documentation](https://github.com/kurttomlinson/oProject/tree/master/Documentation) folder in your favorite web browser.
