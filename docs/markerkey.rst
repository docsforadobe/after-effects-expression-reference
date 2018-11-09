MarkerKey
#########

You can access values for composition markers and layer markers using the same methods. Access layer markers through the thisLayer.marker object; access composition markers through the thisComp.marker object.

For the purpose of expressions, markers are a special type of Key object, so you can use methods such as nearestKey(time) to access markers, and markers also have time and index attributes. The index attribute is not the number (name) of the marker; it is the keyframe index number, representing the order of the marker in the time ruler.

Expressions have access to all the values for a marker that you can set in the Composition Marker or Layer Marker dialog box.

This expression on the Source Text property of a text layer displays the time, duration, index, comment (name), chapter, URL, frame target, and cue point name for the layer marker nearest the current time, and whether the marker is for an event cue point::

	m = thisLayer.marker.nearestKey(time);
	s = "time:" + timeToCurrentFormat(m.time) + "\r" +
        "duration: " + m.duration + "\r" +
        "key index: " + m.index + "\r" +
        "comment:" + m.comment + "\r" +
        "chapter:" + m.chapter + "\r" +
        "URL:" + m.url + "\r" +
        "frame target: " + m.frameTarget + "\r" +
        "cue point name: " + m.cuePointName + "\r" +
        "Event cue point? " + m.eventCuePoint + "\r";
	for (param in m.parameters){
        s += "parameter: " + param + " value: " + m.parameters[param] + "\r";
	}
	s

Because the XMP metadata in a footage item can be converted into layer markers for a layer based on that item, expressions can interact with XMP metadata. For information, see `XMP metadata in After Effects <https://helpx.adobe.com/after-effects/using/xmp-metadata.html#xmp_metadata_in_after_effects>`_.

Dan Ebberts provides a tutorial on the `After Effects Developer Center <http://www.adobe.com/devnet/aftereffects/>`_ that includes an example of using XMP metadata with expressions.

----

Marker.duration
***************
**Description**

Duration, in seconds, of marker.

**Type**

Number

----

Marker.comment
***************
**Description**

Contents of Comment field in marker dialog box.

**Type**

String

----

Marker.chapter
***************
**Description**

Contents of Chapter field in marker dialog box.

**Type**

String

----

Marker.url
***************
**Description**

Contents of URL field in marker dialog box.

**Type**

String

----

Marker.frameTarget
******************
**Description**

Contents of Frame Target field in marker dialog box.

**Type**

String

----

Marker.eventCuePoint
********************
**Description**

Setting for cue point type in marker dialog box. True for Event; false for Navigation.

**Type**

Boolean

----

Marker.cuePointName
*******************
**Description**

Contents of cue point Name field in marker dialog box.

**Type**

String

----

Marker.parameters
*****************
**Description**

Contents of Parameter Name and Parameter Value fields in marker dialog box.

For example, if you have a parameter named “background color”, then you can use the following expression to access its value at the nearest marker::

	thisComp.marker.nearestKey(time).parameters["background color"]

**Type**

Associative array of String values

----

Marker.protectedRegion
**********************
**Description**

State of the Protected Region option in the Composition Marker dialog box. When true, the composition marker behaves as a protected region. Will also return true for protected region markers on nested composition layers, but is otherwise not applicable to layer markers.

Available in After Effects 16.0 or later.

**Type**

Boolean