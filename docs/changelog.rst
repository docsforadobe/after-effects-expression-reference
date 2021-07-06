.. highlight:: javascript
.. _changelog:

Changelog
#########

What's new and changed for expressions?

----

.. _Changelog.17-7:

`After Effects 17.7 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheFebruary2021releaseversion177>`_ (Feb 2021)
*****************************************************************************************************************************************

- Fixed: An issue where expression edits made in the Graph Editor were not applied consistently.

----

.. _Changelog.17-6:

`After Effects 17.6 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJanuary2021releaseversion176>`_ (Jan 2021)
****************************************************************************************************************************************

- Fixed: An issue that could cause an expression to be replaced instead of appending when using expression or property pick-whip.

----

.. _Changelog.17-1-2:

`After Effects 17.1.2 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJuly2020releaseversion1712>`_ (Jul 2020)
****************************************************************************************************************************************

- Fixed: An issue where Markers could not be referenced by name in the JavaScript Expressions Engine.

----

.. _Changelog.17-1:

`After Effects 17.1 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheMay2020releaseversion171>`_ (May 19 2020)
***************************************************************************************************************************************

- Fixed: An issue with Expression editor to auto-complete 'timeToFrames' function.

----

.. _Changelog.17-0-5:

`After Effects 17.0.5 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheMarch2020releaseversion1705>`_ (Mar 2020)
*****************************************************************************************************************************************

- Fixed: An issue where the Link Focus to Layer command produced an expression that did not work with the JavaScript expression engine.

----

.. _Changelog.17-0-2:

`After Effects 17.0.2 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheJanuary2020releaseversion1702>`_ (Jan 2020)
*******************************************************************************************************************************************

- Fixed: An issue where wrong line numbers would be displayed related to errors in JavaScript expressions.

----

.. _Changelog.17-0:

`After Effects 17.0 <https://helpx.adobe.com/after-effects/using/whats-new/2020.html>`_ (Jan 24 2020)
*****************************************************************************************************

- Implemented Dropdown Menu Expression Control
- Expression Editor improvements:

  - You can now use the new scrolling functionality to prevent the scroll from adjusting incorrectly when the box is resized by typing the return character.
  - Prevent numbers from matching in an autocomplete list if the variable begins with a number. Smarter autocomplete prevents from overriding closing brackets and quotes.
  - You can now scale font size for Hi-DPI displays.
  - Graph editor now commits changes in preferences for all the open graph editors.
  - If you enable syntax highlight, the folding icon buttons in the UI now respect the default and background color, or the line numbers color and background color.
- Expression performance improvements:

  - After Effects now attempts to detect an expression that does not change throughout a comp and calculates the expression only once. Load your favorite expression-filled comp and experience the improved performance.
  - Any expression using :ref:`posterizeTime() <Global.posterizeTime>` now calculates only once for the entire comp, not on every frame.
- Added: Extended expressions access to Text properties.

  - Added: :ref:`Text.Font`
  - Added: :ref:`SourceText`
  - Added: :ref:`TextStyle`

----

.. _Changelog.16-1-3:

`After Effects 16.1.3 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects>`_ (Sep 2019)
*******************************************************************************************************************************************

- Fixed: Indentation of curly braces on new lines could be incorrect in the Expressions editor.

----

.. _Changelog.16-1-2:

`After Effects 16.1.2 <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects>`_ (June 2019)
********************************************************************************************************************************************

- Fixed: After Effects crashes when you close a project that has an expression containing an error.
- Fixed: Expression error messages could be truncated in the error ribbon if there were multiple lines of error text to show.
- Fixed: The property, this_Layer had stopped working when using the Legacy ExtendScript expression engine.
- Fixed: Crash when switching the project level expression engine from JavaScript to Legacy ExtendScript.
- Fixed: Crash with expressions that contain calls to Date.toLocaleString().
- Fixed: Crash when editing expressions in the Graph Editor expression field when AutoComplete is disabled.

----

.. _Changelog.16-1:

`After Effects 16.1 (CC 19) <https://helpx.adobe.com/after-effects/kb/fixed-issues.html#BugsfixedintheearlierversionsofAfterEffects>`_ (Apr 2 2019)
***************************************************************************************************************************************************

- Implemented new expression editor
- Fixed: The JavaScript expressions engine does not generate the same random number results as the Legacy ExtendScript engine.
- Fixed: When an expression references the name of a layer in a string or in a Source Text property, the name of the layer is not returned. Instead, it returns [Object].
- Fixed: The :ref:`sampleImage() <Layer.sampleImage>` expression method returns the wrong value if the post-expression value of the property is read by a ScriptUI panel.
- Fixed: Applying the :ref:`createPath() <PathProperty.createPath>` expression via the Expression Language menu auto-fills the (is_Closed) parameter as deprecated snake case instead of camel caseisClosed.
- Fixed: Renaming an effect that is referenced by an expression causes the expression to incorrectly update references to that effect properties when those properties have the same name as the effect.
- Fixed: The Link Focus Distance to Layer, Link Focus Distance to Point of Interest, Create Stereo 3D Rig, and Create Orbit Null commands create expressions that are incompatible with the JavaScript expression engine.
- Fixed: Specific complex, multi-composition expressions cause fast flickering of the expression error warning banner and icons. Note that to fix this, there is a small slowdown in expression evaluation speed for these expressions.

----

.. _Changelog.16-0:

`After Effects 16.0 (CC 19) <https://helpx.adobe.com/after-effects/using/whats-new/2019.html>`_ (Oct 15 2018)
*************************************************************************************************************

- Implemented new Javascript engine
- Added: :ref:`hexToRgb <hexToRgb>`
- Added: :ref:`marker protectedRegion <Marker.protectedRegion>` property

----

.. _Changelog.15-1-2:

`After Effects 15.1.2 <https://helpx.adobe.com/after-effects/kb/bug-fixes-in-after-effects-cc.html>`_ (Jul 16 2018)
*******************************************************************************************************************

- Fixed: If your project contains multiple master properties by the same name, the expressions that refer to the master properties evaluate incorrectly.
- Fixed: The Property Link pick whip incorrectly writes a self-referential expression for the other selected properties.

----

.. _Changelog.15-1:

`After Effects 15.1 <https://helpx.adobe.com/after-effects/using/whats-new/2018.html#AfterEffectsCCApril2018version151release>`_ (Apr 3 2018)
*********************************************************************************************************************************************

- Added: Property Link pick whip
- Added: Support for custom expression function libraries
- Added: Expression access to :ref:`Project`

  - Added: :ref:`Project.fullPath`
  - Added: :ref:`Project.bitsPerChannel`
  - Added: :ref:`Project.linearBlending`

----

.. _Changelog.15-0:

`After Effects 15.0 (CC) <https://community.adobe.com/t5/after-effects/expression-and-scripting-improvements-in-after-effects-october-2017-pdf/td-p/4787866>`_ (Oct 18 2017)
****************************************************************************************************************************************************************************

- Added: Expression access to data in JSON files

  - Added: :ref:`footage sourceText <Footage.sourceText>` attribute
  - Added: :ref:`footage sourceData <Footage.sourceData>` attribute
  - Added: :ref:`footage dataValue <Footage.dataValue>` method
  - Added: :ref:`footage dataKeyCount <Footage.dataKeyCount>` method
  - Added: :ref:`footage dataKeyTimes <Footage.dataKeyTimes>` method
  - Added: :ref:`footage dataKeyValues <Footage.dataKeyValues>` method
- Added: Expression access to path points on masks, Bezier shapes, and brush strokes

  - Added: :ref:`path points <PathProperty.points>` method
  - Added: :ref:`path inTangents <PathProperty.inTangents>` method
  - Added: :ref:`path outTangents <PathProperty.outTangents>` method
  - Added: :ref:`path isClosed <PathProperty.isClosed>` method
  - Added: :ref:`path pointOnPath <PathProperty.pointOnPath>` method
  - Added: :ref:`path tangentOnPath <PathProperty.tangentOnPath>` method
  - Added: :ref:`path normalOnPath <PathProperty.normalOnPath>` method
  - Added: :ref:`path createPath <PathProperty.createPath>` method

----

.. _Changelog.13-6:

`After Effects 13.6 (CC 2015) <https://helpx.adobe.com/after-effects/kb/ae-13-6.html>`_ (Nov 30 2015)
*****************************************************************************************************

- Improved performance of expressions on time-remapped layers. This also reduces rendering time for audio on time-remapped layers with expressions.
- Fixed: Changing the source text of a text layer no longer causes expressions to fail when the name of the text layer was referenced.
- Fixed: After Effects no longer crashes when the graph editor is displayed while processing an time remapping expression.

----

.. _Changelog.13-5:

`After Effects 13.5 (CC 2015) <https://helpx.adobe.com/after-effects/kb/what-s-new-and-changed-in-after-effects-cc-2015--13-5-.html>`_ (Jun 15 2015)
****************************************************************************************************************************************************

- More efficient expression evaluation
- Added: Expression warning banner

----

.. _Changelog.13-2:

`After Effects 13.2 (CC 2014.2) <https://helpx.adobe.com/ca/after-effects/using/whats-new-2014.html>`_ (Dec 16 2014)
********************************************************************************************************************

- Added: :ref:`sourceRectAtTime() <Layer.sourceRectAtTime>` method
- Fixed: :ref:`sampleImage() <Layer.sampleImage>` in an expression no longer disables multiprocessing

----

.. _Changelog.12-1:

`After Effects 12.1 (CC) <https://helpx.adobe.com/after-effects/using/whats-new-12-1.html/>`_ (Sep 8 2013)
**********************************************************************************************************

- Added iris and highlight properties for camera layers to the expression language menu
-
  - Added: :ref:`Camera.irisShape`
  - Added: :ref:`Camera.irisRotation`
  - Added: :ref:`Camera.irisRoundness`
  - Added: :ref:`Camera.irisAspectRatio`
  - Added: :ref:`Camera.irisDiffractionFringe`
  - Added: :ref:`Camera.highlightGain`
  - Added: :ref:`Camera.highlightThreshold`
  - Added: :ref:`Camera.highlightSaturation`

----

.. _Changelog.10-5:

`After Effects 10.5 (CS5.5) <https://helpx.adobe.com/ro/after-effects/user-guide.html/ro/after-effects/using/expression-language-reference.ug.html/>`_ (Apr 11 2011)
********************************************************************************************************************************************************************

- Added: :ref:`Footage.ntscDropFrame`
- Added: `ntscDropFrame` argument to :ref:`timeToCurrentFormat() <timeToCurrentFormat>`
- Added: :ref:`Layer.sourceTime() <Layer.sourceTime>`

----

.. _Changelog.5-5:

`After Effects 5.5 <https://en.wikipedia.org/wiki/Adobe_After_Effects#History/>`_ (Jan 7 2002)
**********************************************************************************************

- Added: Looping via expressions
- Added: Expression controllers

----

.. _Changelog.5-0:

`After Effects 5.0 <https://en.wikipedia.org/wiki/Adobe_After_Effects#History/>`_ (Apr 2001)
********************************************************************************************

- Expressions first added
