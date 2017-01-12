# accessibility

Notes taken from:
https://app.pluralsight.com/library/courses/web-accessibility-meeting-guidelines/exercise-files

## Web Conformance Guidelines
Accessible to people with disabilities
Protection from discrimination lawsuits
Better SEO
Greater overall usability
Future proof yourself

##Section 508
1986 Amendment to Rehabilitation Act of 1973, updated in 1998 and expected to be refreshed soon.

Targeting websites developed or used by the federal government

Quick Reference Guide: 
https://section508.gov/content/learn/standards/quick-reference-guide#1194.22

##WCAG 2.0: Web Content Accessibility Guidelines
Published in 2008 - Global Accessibility Guidelines
Perceivable: Users must be able to perceive the information being presented
Operable: Users must be able to operate the interface
Understandable: Users must be able to understand the information as well as the operation of the user interface.
Robust: Users must be able to access the content as technologies advance.

Each guideline has 3 levels of conformance: A, AA, AAA
Level A: Most basic of web accessibility features
Level AA: Biggest and most common barriers
Level AAA: Highest level of accessibility

You can filter this rules by Levels here to make the list easier to read:
https://www.w3.org/WAI/WCAG20/quickref/?currentsidebar=%23col_customize

##Which to choose?
###WCAG 2.0 Level AA (meeting this guideline aslo covers all of Section 508)
WCAG Pros:
10 years newer, global acceptance

##HTML
###Document Structure and Landmarks:
DocumentStructureAndLandmarks.html = 7 of the 31 checkpoints.

Test Screen Reader:
Open a browser on Mac with Voice Over: Command + F5
Navigate: Control + Option + U
Then hit Right to move to Landmarks or other sections of the page.
Shortcut to Navigate: Control + Option + Command + (Shift to go back) + H

###Lists:
Lists.html
Types: Ordered, Unordered, Description List

###Navigation and Skip Links:
Links.html
Level A 2.4.1 - Bypass Blocks:
We already use Landmarks, but we need something this is good for non screen readers as well (alt input devices, like keyboards). 
Skip Link - Shortcut link directly to the main content.


###Tables:
Tables.html
Dont use them for layout. Duh.
Use table grouping: thead, tfoot, tbody
th vs td
Avoid complex tables: Not great experience for screen readers.

###Forms, Focus, and Color Contrast:
Do not zero out the CSS Outline property. Just use CSS to give it a better glow.

10% of Men are Color Blind
75% of those are red/green deficient. They have a hard time distinguishing these colors from each other.
If we use Red to indicate invalid fields, and Green to indicate valid ones. Then, yeah...

<input type="text" placeholder="Name" />
Once filled out, this field now has a value of whatever the user filled out, instead of "Name". So they don't know what the field was anymore.

Don't put paragraphs of text inside a <form>. Screen readers have a form mode, which might ignore that text.

Tab Index's:
Never set tab index > 0.
-1 = don't want it to focus in the natural tab order. can still be focusable via JS.
0  = Add tabindex to the natural tab order.

Level AA 1.4.3 - Contrast: The visual representation of text has a contrast ratio of 4.5:1. Example: Placeholder text is too light by default.
Level A 3.3.2 - Labels or Instructions: Labels or instructions are provided when content requires user input.
Level A 2.1.1 - Keyboard: All functionality of the content is operable through keyboard interfaces without requiring specific timing for individual keystrokes.
Level AA 2.4.7 - Focus Visible: Any keyboard operable user interface has a mode of operation where the keyboard focus indicator is visible.
Level A 1.4.1 - Use of Color: Color is not used as the only visual means of conveying information. Example: when form errors, don't just put a red border on the fields that error. Say something as well.
Level A 3.3.1 - Error Identification: If an input error is automatically, the item that is in error is identified and the error is described to the user in text.

##Media
Level A 1.1.1 - Non-text Content: All non-text content that is presented tot he user has a text alternative that serves the equivalent purpose.

Images: 
    Use real text instead of images.
    Web router just shows the file name of an image if no alt text is provided. Same with links without title.
    For images that are just for decoration, ommit the alt text value (alt=""). That way screen readers will ignore them all together.
    Don't describe image literally.
    Describe the meaning or purpose of the image.
Background: 
SVG: 
    Add role="img"
    Use the <title>
    Use aria-labelledby referencing the title

Audio:
Transcripts: Use Apple Dictation, Windows Speech Recognition, Google Docs Voice Typing
Level A 1.4.2 - Audio Control: If any audio on the page plays automatically for more than 3 seconds, pause should be available or to controls the volume.

Video:
Captions: embedded, always visible
Closed: can turn on/off
