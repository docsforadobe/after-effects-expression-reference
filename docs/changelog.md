<a id="changelog"></a>

# Changelog

What’s new and changed for expressions?

---

<a id="changelog-25-0"></a>

## [After Effects 25.0](https://helpx.adobe.com/after-effects/using/whats-new/2025.html) (October 2024)

Added many new text style properties and methods for both characters and paragraphs, as well as the ability to control per-character styling through expressions.

- New attributes of .sourceText:
  : - Added: [SourceText.isPointText](text-sourcetext.md#sourcetext-ispointtext)
    - Added: [SourceText.isParagraphText](text-sourcetext.md#sourcetext-isparagraphtext)
    - Added: [SourceText.isHorizontalText](text-sourcetext.md#sourcetext-ishorizontaltext)
    - Added: [SourceText.isVerticalText](text-sourcetext.md#sourcetext-isverticaltext)
- New per-character style properties and methods:
  : - Added: [TextStyle.replaceText()](text-style.md#textstyle-replacetext)
    - Added: [TextStyle.baselineDirection](text-style.md#textstyle-baselinedirection)
    - Added: [TextStyle.setBaselineDirection()](text-style.md#textstyle-setbaselinedirection)
    - Added: [TextStyle.baselineOption](text-style.md#textstyle-baselineoption)
    - Added: [TextStyle.setBaselineOption()](text-style.md#textstyle-setbaselineoption)
    - Added: [TextStyle.digitSet](text-style.md#textstyle-digitset)
    - Added: [TextStyle.setDigitSet()](text-style.md#textstyle-setdigitset)
    - Added: [TextStyle.isLigature](text-style.md#textstyle-isligature)
    - Added: [TextStyle.setLigature()](text-style.md#textstyle-setligature)
    - Added: [TextStyle.tsume](text-style.md#textstyle-tsume)
    - Added: [TextStyle.setTsume()](text-style.md#textstyle-settsume)
    - Added: [TextStyle.verticalScaling](text-style.md#textstyle-verticalscaling)
    - Added: [TextStyle.setVerticalScaling()](text-style.md#textstyle-setverticalscaling)
    - Added: [TextStyle.horizontalScaling](text-style.md#textstyle-horizontalscaling)
    - Added: [TextStyle.setHorizontalScaling()](text-style.md#textstyle-sethorizontalscaling)
    - Added: [TextStyle.lineJoin](text-style.md#textstyle-linejoin)
    - Added: [TextStyle.setLineJoin()](text-style.md#textstyle-setlinejoin)
- New paragraph style properties and methods:
  : - Added: [TextStyle.direction](text-style.md#textstyle-direction)
    - Added: [TextStyle.setDirection()](text-style.md#textstyle-setdirection)
    - Added: [TextStyle.isEveryLineComposer](text-style.md#textstyle-iseverylinecomposer)
    - Added: [TextStyle.setEveryLineComposer()](text-style.md#textstyle-seteverylinecomposer)
    - Added: [TextStyle.firstLineIndent](text-style.md#textstyle-firstlineindent)
    - Added: [TextStyle.setFirstLineIndent()](text-style.md#textstyle-setfirstlineindent)
    - Added: [TextStyle.isHangingRoman](text-style.md#textstyle-ishangingroman)
    - Added: [TextStyle.setHangingRoman()](text-style.md#textstyle-sethangingroman)
    - Added: [TextStyle.justification](text-style.md#textstyle-justification)
    - Added: [TextStyle.setJustification()](text-style.md#textstyle-setjustification)
    - Added: [TextStyle.leadingType](text-style.md#textstyle-leadingtype)
    - Added: [TextStyle.setLeadingType()](text-style.md#textstyle-setleadingtype)
    - Added: [TextStyle.leftMargin](text-style.md#textstyle-leftmargin)
    - Added: [TextStyle.setLeftMargin()](text-style.md#textstyle-setleftmargin)
    - Added: [TextStyle.rightMargin](text-style.md#textstyle-rightmargin)
    - Added: [TextStyle.setRightMargin()](text-style.md#textstyle-setrightmargin)
    - Added: [TextStyle.spaceAfter](text-style.md#textstyle-spaceafter)
    - Added: [TextStyle.setSpaceAfter()](text-style.md#textstyle-setspaceafter)
    - Added: [TextStyle.spaceBefore](text-style.md#textstyle-spacebefore)
    - Added: [TextStyle.setSpaceBefore()](text-style.md#textstyle-setspacebefore)
- Existing style methods updated to allow per-character styles:
  : - Changed: [TextStyle.setFontSize()](text-style.md#textstyle-setfontsize)
    - Changed: [TextStyle.setFont()](text-style.md#textstyle-setfont)
    - Changed: [TextStyle.setFauxBold()](text-style.md#textstyle-setfauxbold)
    - Changed: [TextStyle.setFauxItalic()](text-style.md#textstyle-setfauxitalic)
    - Changed: [TextStyle.setAllCaps()](text-style.md#textstyle-setallcaps)
    - Changed: [TextStyle.setSmallCaps()](text-style.md#textstyle-setsmallcaps)
    - Changed: [TextStyle.setTracking()](text-style.md#textstyle-settracking)
    - Changed: [TextStyle.setLeading()](text-style.md#textstyle-setleading)
    - Changed: [TextStyle.setAutoLeading()](text-style.md#textstyle-setautoleading)
    - Changed: [TextStyle.setBaselineShift()](text-style.md#textstyle-setbaselineshift)
    - Changed: [TextStyle.setApplyFill()](text-style.md#textstyle-setapplyfill)
    - Changed: [TextStyle.setFillColor()](text-style.md#textstyle-setfillcolor)
    - Changed: [TextStyle.setApplyStroke()](text-style.md#textstyle-setapplystroke)
    - Changed: [TextStyle.setStrokeColor()](text-style.md#textstyle-setstrokecolor)
    - Changed: [TextStyle.setStrokeWidth()](text-style.md#textstyle-setstrokewidth)

---

<a id="changelog-17-7"></a>

## [After Effects 17.7](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheFebruary2021releaseversion177) (Feb 2021)

- Fixed: An issue where expression edits made in the Graph Editor were not applied consistently.

---

<a id="changelog-17-6"></a>

## [After Effects 17.6](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJanuary2021releaseversion176) (Jan 2021)

- Fixed: An issue that could cause an expression to be replaced instead of appending when using expression or property pick-whip.

---

<a id="changelog-17-1-2"></a>

## [After Effects 17.1.2](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJuly2020releaseversion1712) (Jul 2020)

- Fixed: An issue where Markers could not be referenced by name in the JavaScript Expressions Engine.

---

<a id="changelog-17-1"></a>

## [After Effects 17.1](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheMay2020releaseversion171) (May 19 2020)

- Fixed: An issue with Expression editor to auto-complete ‘timeToFrames’ function.

---

<a id="changelog-17-0-5"></a>

## [After Effects 17.0.5](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheMarch2020releaseversion1705) (Mar 2020)

- Fixed: An issue where the Link Focus to Layer command produced an expression that did not work with the JavaScript expression engine.

---

<a id="changelog-17-0-2"></a>

## [After Effects 17.0.2](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJanuary2020releaseversion1702) (Jan 2020)

- Fixed: An issue where wrong line numbers would be displayed related to errors in JavaScript expressions.

---

<a id="changelog-17-0"></a>

## [After Effects 17.0](https://helpx.adobe.com/after-effects/using/whats-new/2020.html) (Jan 24 2020)

- Implemented Dropdown Menu Expression Control
- Expression Editor improvements:
  - You can now use the new scrolling functionality to prevent the scroll from adjusting incorrectly when the box is resized by typing the return character.
  - Prevent numbers from matching in an autocomplete list if the variable begins with a number. Smarter autocomplete prevents from overriding closing brackets and quotes.
  - You can now scale font size for Hi-DPI displays.
  - Graph editor now commits changes in preferences for all the open graph editors.
  - If you enable syntax highlight, the folding icon buttons in the UI now respect the default and background color, or the line numbers color and background color.
- Expression performance improvements:
  - After Effects now attempts to detect an expression that does not change throughout a comp and calculates the expression only once. Load your favorite expression-filled comp and experience the improved performance.
  - Any expression using [posterizeTime()](global.md#global-posterizetime) now calculates only once for the entire comp, not on every frame.
- Added: Extended expressions access to Text properties.
  - Added: [Text.Font…](text.md#text-font)
  - Added: [Source Text](text-sourcetext.md#sourcetext)
  - Added: [Text Style](text-style.md#textstyle)

---

<a id="changelog-16-1-3"></a>

## [After Effects 16.1.3](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects) (Sep 2019)

- Fixed: Indentation of curly braces on new lines could be incorrect in the Expressions editor.

---

<a id="changelog-16-1-2"></a>

## [After Effects 16.1.2](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects) (June 2019)

- Fixed: After Effects crashes when you close a project that has an expression containing an error.
- Fixed: Expression error messages could be truncated in the error ribbon if there were multiple lines of error text to show.
- Fixed: The property, this_Layer had stopped working when using the Legacy ExtendScript expression engine.
- Fixed: Crash when switching the project level expression engine from JavaScript to Legacy ExtendScript.
- Fixed: Crash with expressions that contain calls to Date.toLocaleString().
- Fixed: Crash when editing expressions in the Graph Editor expression field when AutoComplete is disabled.

---

<a id="changelog-16-1"></a>

## [After Effects 16.1 (CC 19)](https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects) (Apr 2 2019)

- Implemented new expression editor
- Fixed: The JavaScript expressions engine does not generate the same random number results as the Legacy ExtendScript engine.
- Fixed: When an expression references the name of a layer in a string or in a Source Text property, the name of the layer is not returned. Instead, it returns [Object].
- Fixed: The [sampleImage()](layer-general.md#layer-sampleimage) expression method returns the wrong value if the post-expression value of the property is read by a ScriptUI panel.
- Fixed: Applying the [createPath()](path-property.md#pathproperty-createpath) expression via the Expression Language menu auto-fills the (is_Closed) parameter as deprecated snake case instead of camel caseisClosed.
- Fixed: Renaming an effect that is referenced by an expression causes the expression to incorrectly update references to that effect properties when those properties have the same name as the effect.
- Fixed: The Link Focus Distance to Layer, Link Focus Distance to Point of Interest, Create Stereo 3D Rig, and Create Orbit Null commands create expressions that are incompatible with the JavaScript expression engine.
- Fixed: Specific complex, multi-composition expressions cause fast flickering of the expression error warning banner and icons. Note that to fix this, there is a small slowdown in expression evaluation speed for these expressions.

---

<a id="changelog-16-0"></a>

## [After Effects 16.0 (CC 19)](https://helpx.adobe.com/after-effects/using/whats-new/2019.html) (Oct 15 2018)

- Implemented new Javascript engine
- Added: [hexToRgb](color-conversion.md#hextorgb)
- Added: [marker protectedRegion](markerkey.md#marker-protectedregion) property

---

<a id="changelog-15-1-2"></a>

## [After Effects 15.1.2](https://helpx.adobe.com/after-effects/kb/bug-fixes-in-after-effects-cc.html) (Jul 16 2018)

- Fixed: If your project contains multiple master properties by the same name, the expressions that refer to the master properties evaluate incorrectly.
- Fixed: The Property Link pick whip incorrectly writes a self-referential expression for the other selected properties.

---

<a id="changelog-15-1"></a>

## [After Effects 15.1](https://helpx.adobe.com/after-effects/using/whats-new/2018.html#AfterEffectsCCApril2018version151release) (Apr 3 2018)

- Added: Property Link pick whip
- Added: Support for custom expression function libraries
- Added: Expression access to [Project](project.md#project)
  - Added: [Project.fullPath](project.md#project-fullpath)
  - Added: [Project.bitsPerChannel](project.md#project-bitsperchannel)
  - Added: [Project.linearBlending](project.md#project-linearblending)

---

<a id="changelog-15-0"></a>

## [After Effects 15.0 (CC)](https://community.adobe.com/t5/after-effects/expression-and-scripting-improvements-in-after-effects-october-2017-pdf/td-p/4787866) (Oct 18 2017)

- Added: Expression access to data in JSON files
  - Added: [footage sourceText](footage.md#footage-sourcetext) attribute
  - Added: [footage sourceData](footage.md#footage-sourcedata) attribute
  - Added: [footage dataValue](footage.md#footage-datavalue) method
  - Added: [footage dataKeyCount](footage.md#footage-datakeycount) method
  - Added: [footage dataKeyTimes](footage.md#footage-datakeytimes) method
  - Added: [footage dataKeyValues](footage.md#footage-datakeyvalues) method
- Added: Expression access to path points on masks, Bezier shapes, and brush strokes
  - Added: [path points](path-property.md#pathproperty-points) method
  - Added: [path inTangents](path-property.md#pathproperty-intangents) method
  - Added: [path outTangents](path-property.md#pathproperty-outtangents) method
  - Added: [path isClosed](path-property.md#pathproperty-isclosed) method
  - Added: [path pointOnPath](path-property.md#pathproperty-pointonpath) method
  - Added: [path tangentOnPath](path-property.md#pathproperty-tangentonpath) method
  - Added: [path normalOnPath](path-property.md#pathproperty-normalonpath) method
  - Added: [path createPath](path-property.md#pathproperty-createpath) method

---

<a id="changelog-13-6"></a>

## [After Effects 13.6 (CC 2015)](https://helpx.adobe.com/after-effects/kb/ae-13-6.html) (Nov 30 2015)

- Improved performance of expressions on time-remapped layers. This also reduces rendering time for audio on time-remapped layers with expressions.
- Fixed: Changing the source text of a text layer no longer causes expressions to fail when the name of the text layer was referenced.
- Fixed: After Effects no longer crashes when the graph editor is displayed while processing an time remapping expression.

---

<a id="changelog-13-5"></a>

## [After Effects 13.5 (CC 2015)](https://helpx.adobe.com/after-effects/kb/what-s-new-and-changed-in-after-effects-cc-2015--13-5-.html) (Jun 15 2015)

- More efficient expression evaluation
- Added: Expression warning banner

---

<a id="changelog-13-2"></a>

## [After Effects 13.2 (CC 2014.2)](https://helpx.adobe.com/ca/after-effects/using/whats-new-2014.html) (Dec 16 2014)

- Added: [sourceRectAtTime()](layer-sub.md#layer-sourcerectattime) method
- Fixed: [sampleImage()](layer-general.md#layer-sampleimage) in an expression no longer disables multiprocessing

---

<a id="changelog-12-1"></a>

## [After Effects 12.1 (CC)](https://helpx.adobe.com/after-effects/using/whats-new-12-1.html/) (Sep 8 2013)

- Added iris and highlight properties for camera layers to the expression language menu
- - Added: [Camera.irisShape](camera.md#camera-irisshape)
  - Added: [Camera.irisRotation](camera.md#camera-irisrotation)
  - Added: [Camera.irisRoundness](camera.md#camera-irisroundness)
  - Added: [Camera.irisAspectRatio](camera.md#camera-irisaspectratio)
  - Added: [Camera.irisDiffractionFringe](camera.md#camera-irisdiffractionfringe)
  - Added: [Camera.highlightGain](camera.md#camera-highlightgain)
  - Added: [Camera.highlightThreshold](camera.md#camera-highlightthreshold)
  - Added: [Camera.highlightSaturation](camera.md#camera-highlightsaturation)

---

<a id="changelog-10-5"></a>

## [After Effects 10.5 (CS5.5)](https://helpx.adobe.com/ro/after-effects/user-guide.html/ro/after-effects/using/expression-language-reference.ug.html/) (Apr 11 2011)

- Added: [Footage.ntscDropFrame](footage.md#footage-ntscdropframe)
- Added: ntscDropFrame argument to [timeToCurrentFormat()](time-conversion.md#timetocurrentformat)
- Added: [Layer.sourceTime()](layer-sub.md#layer-sourcetime)

---

<a id="changelog-5-5"></a>

## [After Effects 5.5](https://en.wikipedia.org/wiki/Adobe_After_Effects#History/) (Jan 7 2002)

- Added: Looping via expressions
- Added: Expression controllers

---

<a id="changelog-5-0"></a>

## [After Effects 5.0](https://en.wikipedia.org/wiki/Adobe_After_Effects#History/) (Apr 2001)

- Expressions first added
