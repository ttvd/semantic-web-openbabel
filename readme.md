Semantic Web Plugin for OpenBabel  
---------------------------------
Previously hosted at https://code.google.com/p/semanticwebopenbabel/  


**Introduction**

You should be able to use the OWL/RDF plugin just like any other Open Babel plugin (the only limitation is that it's a write-only plugin at the moment).

**Usage**  
The general usage is:

[ob_executable] -i [input_format] [input_file] -oowl [owl_file] -q [config_file]  

-q argument is optional, if it's skipped, configuration will be read from OwlPluginConfiguration.xml file, which should be located in the same directory as the Open Babel executable.

**Examples**  
Here we assume that 'babel' is the name of our Open Babel executable.

Read CID_1549520.sdf, write to CID_1549520.owl, use owl_conf2.xml as config:  
-> babel -isdf CID_1549520.sdf -oowl CID_1549520.owl -q”owl_conf2.xml”  

Read CID_1549520.sdf, write to CID_1549520.owl, use OwlPluginConfiguration.xml as config:  
-> babel -isdf CID_1549520.sdf -oowl CID_1549520.owl  

Read CID_1549520.sdf and output resulting owl file to console:  
-> babel -isdf CID_1549520.sdf -oowl

**Current Limitations**

Currently the OWL generator plugin is a write-only plugin, meaning it can output RDF/OWL files, however it cannot read these back into the Open Babel data model. Although, having the initial configuration file (which was used during the generation stage) it should not be difficult to do the reverse procedure. An interesting option would be to embed the original configuration file as a comment inside the generated OWL ontology, so it could later be used to read the data back into the Open Babel data model.

In this project we haven’t addressed several things which might eventually prove to be useful: for example, ability to tell plugin to “close the world” and ability to generate Qualified Cardinality Restrictions (QCRs).

**Copyright**  

Mykola Konyk, 2008

**License**  

This plugin has same license as OpenBabel, which is GPL.
