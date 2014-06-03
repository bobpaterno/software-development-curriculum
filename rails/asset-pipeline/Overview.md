#Overview of Asset Pipeline
==========================
##What is The Asset Pipeline

The asset pipeline is one of the biggest new features in Rails 3.1 that was designed to manage your Rails applications’ assets. 
The asset pipeline provides a framework to concatenate and minify or compress JavaScript and CSS assets. 
It also adds the ability to write these assets in other languages and pre-processors such as CoffeeScript, Sass and ERB.

==========================
##Good to know

*At its most basic the asset pipeline is a list of loadpaths. You can see this list by running the console and viewing Rails.application.config.assets.paths.

*The asset pipeline is technically no longer a core feature of Rails 4, it has been extracted out of the framework into the sprockets-rails gem.

===========================
##A Few Notible Features

- Preprocessing

Is handled by the "Tilt" gem. To utilize preprocessing you'll add another extension to a static file's name and specify a processor, for example .erb. 
You can now add ERB code to this file and it will be processed. For example, when a file has an .scss extension this is treated as a preprocessor extension and the file will be passed through the SASS processor. 

(erb stands for "Embedded RuBy". A .html.erb or .erb.html file is HTML with Ruby code embedded in; Rails will evaluate the Ruby to add content to the file dynamically, and will output a "pure" HTML file for rendering.)


- Managing Assets With Sprockets

Sprockets handles dependency management in Rails. Sprockets is a tool for managing libraries of JavaScript (and CoffeeScript) code, declaring dependency management and include 3rd-party code. At its core, Sprockets makes a require method available inside your .js and .coffee files which can pull in the contents of an external file from your project or from a 3rd party gem.

Sprockets will concatenate all JavaScript files into one master .js file and all CSS files into one master .css file. You can customize this strategy to group files any way you like. In production, Rails inserts an MD5 fingerprint into each filename so that the file is cached by the web browser. You can invalidate the cache by altering this fingerprint, which happens automatically whenever you change the file contents.

- Fingerprinting

Fingerprinting is a technique that makes the name of a file dependent on the contents of the file. When the file contents change, the filename is also changed. For content that is static or infrequently changed, this provides an easy way to tell whether two versions of a file are identical, even across different servers or deployment dates.
The technique sprockets uses for fingerprinting is to insert a hash of the content into the name, usually at the end. For example a CSS file global.css

##Great! So how do I use The Asset Pipeline?

In previous versions of Rails, all assets were located in subdirectories of public such as images, javascripts and stylesheets. With the asset pipeline, the preferred location for these assets is now the app/assets directory. Files in this directory are served by the Sprockets middleware.

Assets can still be placed in the public hierarchy. Any assets under public will be served as static files by the application or web server. You should use app/assets for files that must undergo some pre-processing before they are served.

In production, Rails precompiles these files to public/assets by default. The precompiled copies are then served as static assets by the web server. The files in app/assets are never served directly in production.

##Further Reading

Rails Assets Pipeline Cheat Sheet (Github gist:7332590)

##Sources

http://guides.rubyonrails.org/asset_pipeline.html

===========================
Tutorials Point: 

http://asciicasts.com/episodes/279-understanding-the-asset-pipeline

