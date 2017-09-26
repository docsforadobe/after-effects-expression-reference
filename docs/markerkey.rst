MarkerKey
#########

You can access values for composition markers and layer markers using the same methods. Access layer markers through the thisLayer.marker object; access composition markers through the thisComp.marker object.

For the purpose of expressions, markers are a special type of Key object, so you can use methods such as nearestKey(time) to access markers, and markers also have time and index attributes. The index attribute is not the number (name) of the marker; it is the keyframe index number, representing the order of the marker in the time ruler.

Expressions have access to all the values for a marker that you can set in the Composition Marker or Layer Marker dialog box. This expression on the Source Text property of a text layer displays the time, duration, index, comment (name), chapter, URL, frame target, and cue point name for the layer marker nearest the current time, and whether the marker is for an event cue point:

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

Because the XMP metadata in a footage item can be converted into layer markers for a layer based on that item, expressions can interact with XMP metadata. For information, see XMP metadata in After Effects.

Dan Ebberts provides a tutorial on the After Effects Developer Center that includes an example of using XMP metadata with expressions.

duration
Return type: Number. Duration, in seconds, of marker.

comment
Return type: String. Contents of Comment field in marker dialog box.

chapter
Return type: String. Contents of Chapter field in marker dialog box.

url
Return type: String. Contents of URL field in marker dialog box.

frameTarget
Return type: String. Contents of Frame Target field in marker dialog box.

eventCuePoint
Return type: Boolean. Setting for cue point type in marker dialog box. True for Event; false for Navigation.

cuePointName
Return type: String. Contents of cue point Name field in marker dialog box.

parameters
Return type: associative array of String values. Contents of Parameter Name and Parameter Value fields in marker dialog box.For example, if you have a parameter named “background color”, then you can use the following expression to access its value at the nearest marker:  thisComp.marker.nearestKey(time).parameters["background color"]
