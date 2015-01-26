

This is an long introduction to the "level 0" script , not only how the scripts  works, but also a description of the main concepts behind the script. it assumes that you are using Best Practical "Request Tracker for incident Response" to handle the security incidents, and also it assumes that most of the incidents came directly to your "incident & report queue by email.

This project has three main blocks:

1. A library, based on Perl module RT::Client::REST to interacts with a remote RT installation

2. A language, to define how to handle a Incident Report and what actions to perform with it.

3. A command line tool (level0) to intectact with a remote RTIR installation.

Module interelation

level0.pl: Is a perl script / program that is a test implementation, it will ask for the RT credentials, load an XML file with actions and be able to process the tickets in the Incident Report queue and execute the actions defined in IHL to be executeed.
	- Cmd.pm , perl module generated from the cmd.yp grammar, it implements a command line interface to the language, this language is different from the IHL language that is used to do the task.
	- Help.pl : Help module called from cmd.pm to show the action.
	-Actions : it implements most of the actions , mostly it's a wrapper for rtactions.
	
	- Ihl.pm, it implements the incident handling language, that is used to perform actions on a ticket, its generated from the grammpar in ihl.yp, internally it uses
		- Ihlc.pm , auxiliary function for ihl.pm
		- Rtactions: Low level access to RT::Client::Rest




