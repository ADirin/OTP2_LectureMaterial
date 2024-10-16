# Home Assignment (Optional)

## Step 1: Create a JavaFX Project

1. Open your preferred Integrated Development Environment (IDE) for Java development.
2. Create a new JavaFX project or open an existing one where you want to add this feature.

   Just click create (No need to select any libraries).

   ![New Project](/Images/jfxh1.png)

4. Right-click the FXML file and open the file through Scene Builder. (If you do not have it installed yet, you need to search for it on Google to install it).

   ![New Project](/Images/jfxh2.png)

5. Remove the Hello buttons and the label, then add three buttons as shown in the following figures.

   ![New Project](/Images/jfxh3.png)
   
   You may change the text of the button on the right side of the screen in the properties tab.

   ![New Project](/Images/jfxh4.png)

7. In Scene Builder, go to **File** and save the changes you made above.
8. Get back to the IntelliJ project and add a bundle as shown in the figure below:

   ![New Project](/Images/jfxh5.png)

   Add only a bundle without defining a language or a country.

   ![New Project](/Images/jfxh6.png)

10. Add the following buttons in `bundle1` (see below):

   ![New Project](/Images/jfxh7.png)

   Open the `Hello-view.fxml` and do the following modifications:

   1. Add the `fx:id` for each button if Scene Builder does not create it:

```xml
<children>
    <Button mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 1"/>
    <Button mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 2"/>
    <Button mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 3"/>

  </children>
``` 

   Add manually the `fx:id`.
```xml
<children>
    <Button fx:id="button1" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 1"/>
    <Button fx:id="button2" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 2"/>
    <Button fx:id="button3" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="button 3"/>

  </children>
```

   3. Create three button-type objects in the `HelloController` as shown in the following figure:

![New Project](/Images/jfxh8.png)

   5. Add an `initialize` method to initialize the buttons through the resource bundle as shown in the figure:

```java
   public void initialize() {
       ResourceBundle bundle = ResourceBundle.getBundle("bundle1");
       button1.setText(bundle.getString("button1.text"));
       button2.setText(bundle.getString("button2.text"));
       button3.setText(bundle.getString("button3.text"));
   }
```
  4. Run the code and make sure the button labels are updated from bundle1, as shown in the following figure.

 ![New Project](/Images/jfxh9.png)

----------------------

## Phase II
  1. Add another bundle as shown in the figure below.

 ![New Project](/Images/jfxh10.png)

  3. Copy the text from bundle1 to bundle2 and change it in bundle2 as indicated in the following figure:

*Note:* There should not be a space between buttons and number (e.g., button1, button2, button3).

![New Project](/Images/jfxh11.png)

  3. Change the ResourceBundle file in the initialize method to bundle2. See the figure below.

![New Project](/Images/jfxh12.png)

  4. Run and make sure that bundle2 is selected for ResourceBundle. See figure below.

![New Project](/Images/jfxh13.png)

------------------------

## Phase III

  1. Comment out the statements inside the initialize method as shown in the figure below.

```java
public void initialize(){
        //ResourceBundle bundle = ResourceBundle.getBundle("bundle2");
        //button1.setText(bundle.getString(button1.text));
        //button2.setText(bundle.getString(button2.text));
        //button3.setText(bundle.getString(button3.text));
        
}

```
  2. Open the HelloApplication file and make the following modifications:

```java
FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
fxmlLoader.setResources(ResourceBundle.getBundle("bundle1"));
Scene scene = new Scene(fxmlLoader.load(), 320, 240);
stage.setTitle("Hello!");
stage.setScene(scene);
stage.show();

```
  3. Change the Hello-view.fxml file and add %button1.text in the Text tags. The changes are highlighted in yellow color:

```xml
<children>
    <Button fx:id="button1" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="%button1.text" />
    <Button fx:id="button2" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="%button2.text" />
    <Button fx:id="button3" mnemonicParsing="false" prefHeight="26.0" prefWidth="267.0" text="button 3" />
</children>
```

  4. Run the code and see the changes. In the screenshots below, the button 3 is not set as a variable (%button3.text) just to demonstrate the behavior of the % for the other two buttons.

![New Project](/Images/jfxh15.png)

----------------------------------------------------------

## Phase IV
  1. Modify also button 3 in hello-view.fxml as shown to other two buttons:

   ```xml
<children>
    <Button fx:id="button1" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="%button1.text" />
    <Button fx:id="button2" mnemonicParsing="false" prefHeight="26.0" prefWidth="270.0" text="%button2.text" />
    <Button fx:id="button3" mnemonicParsing="false" prefHeight="26.0" prefWidth="267.0" text="%button3.text" />
</children>
  ```
  2. Add a Bundle with the following three languages by using the + sign (EN, IR, JP).

  3. Modify the bundle which you have just created.

  4. Modify and add an action method to the buttons in hello-view.fxml.

  5. Point the mouse to the newly created actions and select Create Method (see the screenshots below):

Follow for all three onAction buttons.

  6. Open the HelloController and make sure you have already created the three methods.

  7. Create a method and call it loadView in your HelloController as shown below. Copy the FXMLLoader from the start method in HelloApplication:


```java
FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
fxmlLoader.setResources(ResourceBundle.getBundle("bundle1"));
Scene scene = new Scene(fxmlLoader.load(), 320, 240);

```
And paste it in the loadView method and change the ResourceBundle to getBundle("bundle", locale):

```java
public void loadView(Locale locale) throws IOException {
    FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
    fxmlLoader.setResources(ResourceBundle.getBundle("bundle", locale));
}
```
  8. Create a Locale object in each button's methods (see below):

   Repeat the same steps for the other two buttons.

  9. In the loadView method, remove the Scene statement and add:

```java
Parent root = fxmlLoader.load();

```
  10. Remove the IOException from the method and just use try-catch after the Parent statement, see the final loadView() method below:

```java
public void loadView(Locale locale) {
    FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
    fxmlLoader.setResources(ResourceBundle.getBundle("bundle", locale));
    try {
        Parent root = fxmlLoader.load();
    } catch (IOException e) {
        e.printStackTrace();
    }
}

```

  11. Finally, add the Stage after the Parent statement to load the stage:

```java
public void loadView(Locale locale) {
    FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
    fxmlLoader.setResources(ResourceBundle.getBundle("bundle", locale));
    try {
        Parent root = fxmlLoader.load();
        Stage s = (Stage) button1.getScene().getWindow();
        s.setScene(new Scene(root));
    } catch (IOException e) {
        e.printStackTrace();
    }
}


```

  12.  Run the application.

  *Note:* If you see a question mark for Persian and Japanese, ensure to select the UTF-8 formatting from File → Settings → Editor → File Encoding.

  13. Make sure the font in the corresponding bundle is properly translated and not displayed as ???.

  If that is the case, use Google Translate to get the correct translation.

  14. Run again.

------------------------

# YOUR Task

Revise the interface to include a label at the bottom of the third button. This label should display your name and the current time following the language selected.

Please submit a screenshot of the updated interface for each language option and compile them into a single PDF file.
