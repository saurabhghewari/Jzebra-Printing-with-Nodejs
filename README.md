jZebra To Print using the Browsers.

Pre-Requisites:-
	1. Backend Web Server apace/tomacat/Node etc.
		*This demo uses Nodejs server.
	2. Java greater than 1.5v.
		Get the java versions using this command from cmd:- java -version
		Or Update java to the latest versions.
	3. Firefox with java plugins.(Strictly recommended)
		Test the browser for the java plugin or else update the browser with the java plugin.
	4. Windows Or Linux

**Note:- Downloding or cloning this repository need not to follow the below steps.
          Just run these commnds one after one 
            cd folder_name 
            npm install 
            npm start

Getting the jzebra lib:-
	1. Download the jzebra library form the 
		https://code.google.com/p/jzebra/downloads/list
	2. Extract it to the folder of your name.

setting up the Thermal printer:-(Connect the printer using USB)
	Follow the steps from this link depending which OS you are using:-
		https://code.google.com/p/jzebra/wiki/TutorialWebApplet
	*Note for Windows:- You get the driver cd with the printer, install the drivers for the printer you have. If drivers are not available then follow the documentation from above link.

Setting up the Backend server(Nodejs)
	*Note:- You can setup your own backend server as you just have to server the required printing libs and files to the client.
	1. Considering Nodejs and Express are installed on the machine, run this cmd
		express project_name
		cd project_name
		npm install
		npm start - just to check all is set by putting the http://localhost:3000 in firefox.
	2. Here comes the actual flow:-
		A. Put all files in the public folder
			These file can be found under the extracted jzebra folder. 
				jzebra_extracted_folder/qz-print/dist/qz-print.jar
				jzebra_extracted_folder/qz-print/dist/qz-print_jnlp.jnlp
				jzebra_extracted_folder/qz-print/dist/js/*
		For Example:-
			app
				-public
					..
					javascripts
						---jzebra_extracted_folder/qz-print/dist/js/*
					qz-print.jar
					qz-print_jnlp.jnlp
				-views
					.html file which contains the print logic.(here print.html)
					print.html is sample.html found here
						jzebra_extracted_folder/qz-print/dist/sample.html
	3. Then in main file of server ex:- app.js or server.js make the changes to serve 		the print.html page.

	4. Then going to http://localhost:3000/ the firefox should ask for the blocked content permission. Allow the blocked content then you should get the error or nothing should go for the print on clicking any print button.

	5. Now open the java control panel and go to security tab. At the bottom you will get Edit List button to Exception Sites block.

	6. Here Add the such page links whcih executes the applet code. 
		In this Example
			http://localhost:3000
			http://localhost:3000/qz-printer(optional, it the error continues)
		Also check for the security level. Set Medium or High
	7. Save the above settings.
	8 Restart the firefox browser and re-run the url. This should work now which will prompt for the security block asking the permission to run the applet.

Full Working with source code is here 
	

**For more info follow the jzebra code.google.com/p/jzebra
