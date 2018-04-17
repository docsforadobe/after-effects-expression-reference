Project
################################################

Project.fullPath
*********************************************
**Description**

The platform-specific absolute file path, including the project file name. If the project has not been saved, it returns an empty string.

Example::

	thisProject.fullPath

**Type**

String

----

Project.bitsPerChannel
*********************************************
**Description**

The color depth of the project in bits per channel (bpc), as set in *Project Settings > Color Management*
They are one of `8`, `16`, or `32`. Equivalent to the scripting project attribute `app.project.bitsPerChannel`.


Example::

	thisProject.bitsPerChannel

**Type**

Number

----

Project.linearBlending
*********************************************
**Description**

The state of the Blend Colors Using 1.0 Gamma option in *Project Settings > Color Management*.
Equivalent to the scripting project attribute `app.project.linearBlending`.

Example::

	thisProject.linearBlending

**Type**

Boolean
