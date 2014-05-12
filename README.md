Javascript Thaana Keyboard is a brkeyboard handler for Javascript browser environments that translates key input into the appropriate Unicode Thaana characters. Hence, it makes it possible for HTML text input and textarea fields (and similar) to accept Thaana without having to require the user to switch the keyboard language on their computer. Such a feature contributes for a better user experience as the user can simply enter Dhivehi in Thaana without the extra hassle.

## Keyboard support
JTK now supports the following keyboard layouts:

Phonetic (Segha version): This keyboard is perhaps the most popular Thaana keyboard layout. JTK identifies this keyboard as "phonetic".

Phonetic (Hassan Hameed version): This keyboard is similar to above but notably differs in its mapping of alifu, abafili, aabaafili, gaafu and the sukun. JTK identifies this keyboard as 'phonetic-hh'.

Typewriter: This is the standardized Thaana layout used on typewriters. JTK identifies this keyboard as 'typewriter'.

## Browser support
JTK should work perfectly well on:
- Microsoft Internet Explorer 5.5+
- Mozilla Firefox 1+
- Opera 9+
- Apple Safari 2+
- Google Chrome 0.1+.

## Basic usage
The basic usage allows for fast and easy integration of JTK on your Thaana web pages.

1. Link the file in the HEAD section of the page:
```html
<script type="text/javascript" src="jtk-4.0.packed.js"></script>
```

2. For any element accepting input (i.e. INPUTs, TEXTAREAs, content-editable DIVs), assign them the special class name "thaanaKeyboardInput". JTK will automatically handle text entry to any element with that class name. You can assign further classes to the elements without ill-effect, if needed.

3. There are two ways to set the keyboard used for an element.

### defaultKeyboard method
This method allows setting a default keyboard to be used on all elements handled by JTK. To do this, add the following to the HEAD section of your web page but make sure it is added after the code inserted from step 1 above.

```html
<script type="text/javascript">
// Default mode: 'off', 'phonetic', 'phonetic-hh', 'typewriter'
thaanaKeyboard.defaultKeyboard = 'phonetic';
</script>
```

### thaanaKeyboardState method
This method allows per element control on the type of keyboard used by an element handled by JTK. To do this, add a form element (can be a radio, checkbox, select, hidden or text field) with its name set to the text entry element id suffixed with the string "_thaanaKeyboardState". The value of these fields should specify either 'off', 'phonetic', 'phonetic-hh' or 'typewriter', indicating the status and the keyboard in use.

So, if you had a text entry field with the id "fullname" then the keyboard could be specified using a hidden field as follows:
```html
<input type="text" class="thaanaKeyboardInput" id="fullname">
<input type="hidden" name="fullname_thaanaKeyboardState" value="phonetic">
```

4. Make sure that the text direction for the Thaana fields is set to "rtl". This can be easily achieved using CSS, by adding a class definition for the "thaanaKeyboardInput" class or by any other method of your choice. Adding the following to your CSS definition should suffice for most uses:
```css
.thaanaKeyboardInput {
    font-family: faruma, 'mv iyyu nala', 'mv elaaf normal';
    direction: rtl;
}
```

If the above instructions are followed correctly, the JTK Thaana functionality would be in effect soon as the page has loaded!

## Advanced Usage: The JTK object, methods and properties
To facilitate advanced integration functionality for developers looking to have (finer) control over its behavior, JTK now makes itself available as a public object named "thaanaKeyboard". 

The following properties and methods exposed by the "thaanaKeyboard" object:

defaultKeyboard: [property] The Thaana keyboard layout type to default to when JTK enabled elements do not have a keyboard specified.
Valid values are: 'off' to keep Thaana disabled, 'phonetic' to use the standard phonetic layout, 'phonetic-hh' to use the phonetic layout by Dr. Hassan Hameed and 'typewriter' to use the typewriter layout.

setHandlerById ( id, action ): [method] Sets the state of the JTK handler for a page element.
The id argument should be a string containing the id of any content-editable element. The action argument should specify either "enable" or "disable" depending on whether input handling for Thaana should be enabled or disabled, respectively.

setHandlerByClass ( class, action ): [method] Sets the state of the JTK handler for a set of page elements.
The class argument should be a string containing the class name of any content-editable element (i.e input, textarea etc). The action argument should specify either "enable" or "disable" depending on whether input handling for Thaana should be enabled or disabled, respectively.

## Updates/History
http://www.jawish.org/blog/plugin/tag/javascript+thaana+keyboard

## Demo
Demo: http://www.jawish.org/blog/uploads/jtk-4.2.1-test.html

## License
JTK is released under the MIT License, allowing its use in both personal and commercial applications as long as the copyright and license permission notice remains intact.
