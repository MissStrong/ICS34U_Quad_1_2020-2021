## User-Friendly GUIs

Many GUIs do the following by default:

* Don't allow users to submit invalid inputs.
* Automatically place the cursor inside the first text box when the GUI is first constructed.
* Have the default button be a different colour than the rest of the buttons.
* Allow users to press ENTER in place of pushing the default button.


### Invalid Inputs

In general, you should not trust that the user will follow the instructions. Be prepared for them to do something wrong. For example, if the user enters "February 47th, Year 2018.5", you don't want your program to proceed as if that were a valid date. Display an error message when they do something wrong, or use a more appropriate method of input, such as a dropdown menu.


### Cursor Placement

You can use `textBoxName.requestFocus();` (with `textBoxName` being the name of the text box) such as a text field or a text area, to move the cursor there. In general, the less the user has to use their mouse, the better. 


### Coloured Buttons

You can change the colour of a button. For example, if there is one button that should stand out more than the others, you can make it a darker colour to make it stand out more. You can look up the RGB or hex value of the colour you want.

```Java
button.setForeground(new Color(58, 86, 34));
```


### Key Listening

The action listeners you've been using for buttons "listen" for when the button is pressed or released. You can also make them "listen" for a specific key to be pressed or released.

You can allow a user to press ENTER to perform the same action of pressing a button. 

```java
textFieldName.addKeyListener(new KeyAdapter() { // Replace textFieldName with the actual name of the text field
  public void keyReleased(KeyEvent evt) {
    // VK_Enter is the key code for the ENTER key
    if (evt.getKeyCode() == VK_ENTER) {
      // Do something here
    }
  }
});
```
Note that when you use this, you need to also put `import static java.awt.event.KeyEvent.*;` at the top of the file.
