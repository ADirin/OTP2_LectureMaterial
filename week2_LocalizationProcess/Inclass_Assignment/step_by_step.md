
# JavaFX Multilingual Application Guide

## Step 1: Create a JavaFX Project
1. Open your preferred Integrated Development Environment (IDE) for Java development.
2. Create a new JavaFX project or open an existing one where you intend to incorporate this feature.
3. Simply click on "Create" without selecting any additional libraries.

![New Project](/Images/jfx1.png)

## Step 2: Modify the FXML File
1. Open the `hello-view.fxml` file.

![New Project](/Images/jfx2.png)

3. Add four buttons and a label to the layout as shown below:


```xml
   <VBox prefHeight="186.0" prefWidth="239.0" spacing="20.0" xmlns="http://javafx.com/javafx/21" xmlns:fx="http://javafx.com/fxml/1" fx:controller="org.example.demo2.HelloController">
       <padding>
           <Insets bottom="20.0" left="20.0" right="20.0" top="20.0" />
       </padding>
       
       <Button fx:id="btnEN" onAction="#onbtnENClick" text="EN" />
       <Button fx:id="btnFR" onAction="#onbtnFRClick" text="FR" />
       <Button fx:id="btnJP" onAction="#onbtnJPClick" text="JP" />
       <Button fx:id="btnIR" onAction="#onbtnIRClick" text="IR" />
       <Label fx:id="lbl" alignment="CENTER" prefHeight="18.0" prefWidth="210.0" text="  ? ">
           <font>
               <Font size="18.0" />
           </font>
       </Label>
       <Label fx:id="welcomeText" />
   </VBox>
```
3. If you encounter an error for any component, ensure to import the necessary classes.

![New Project](/Images/jfx3.png)

5. Create methods for each button (onbtnENClick, onbtnFRClick, onbtnJPClick, onbtnIRClick).

![New Project](/Images/jfx4.png)

## Step 3: Modify the Controller Class

![New Project](/Images/jfx5.png)

1. Open the HelloController class.
2. Update the content of the HelloController class as shown below.

![New Project](/Images/jfx6.png)

## Step 4: Implement Button Click Methods in HelloController
- For each button (btnEN, btnFR, btnJP, btnIR), create corresponding methods annotated with @FXML to specify the onAction event.

- Each method will handle the language change logic when its respective button is clicked.

- Implement logic to change the language by using the ResourceBundle class to load language-specific properties files (e.g., message_en.UK.properties, message_fr.FR.properties).

- Update the welcomeText label with the appropriate greeting message from the loaded resource bundle.

```java
public class HelloController {

    // Injected Label for displaying welcome text
    @FXML
    private Label welcomeText;

    // Injected Label for displaying additional messages
    @FXML
    private Label lbl;

    // ResourceBundle for loading language-specific messages
    private ResourceBundle bundle;

    // Locale for specifying language and country
    private Locale locale;

    // Method to handle button click event for "Hello" button
    @FXML
    protected void onHelloButtonClick() {
        welcomeText.setText("Welcome to JavaFX Application!");
    }

    // Method to load language-specific messages based on language and country
    @FXML
    private void loadLanguage(String lang, String country) {
        locale = new Locale(lang, country);
        bundle = ResourceBundle.getBundle("message", locale);
        lbl.setText(bundle.getString("greeting"));
    }

    // Method to handle button click event for English language button
    @FXML
    public void onbtnENClick(ActionEvent actionEvent) {
        loadLanguage("en", "UK");
    }

    // Method to handle button click event for French language button
    @FXML
    public void onbtnFRClick(ActionEvent actionEvent) {
        loadLanguage("fr", "FR");
    }

    // Method to handle button click event for Japanese language button
    @FXML
    public void onbtnJPClick(ActionEvent actionEvent) {
        loadLanguage("ja", "JP");
    }

    // Method to handle button click event for Persian language button
    @FXML
    public void onbtnIRClick(ActionEvent actionEvent) {
        loadLanguage("fa", "IR");
    }
}


```
## Step 5: Add Resource Bundles
1. Select the source directory and create properties files for each language.

![New Project](/Images/jfx7.png)

3. For each file (e.g., message_en.UK.properties, message_fr.FR.properties), add appropriate greeting messages.

![New Project](/Images/jfx8.png)

![New Project](/Images/jfx9.png)

![New Project](/Images/jfx10.png)

## Step 6: Run the Application

1. Build and run your JavaFX application (e.g., HelloApplication).

![New Project](/Images/jfx11.png)

3. The application window should display buttons for different languages (EN, FR, JP, IR) and a label for greetings.

![New Project](/Images/jfx12.png)

5. Click each button to confirm the language changes, and the greeting message updates accordingly.

-----------------------------------------------------------------------------------------------------------
### Note:
1. Make sure you have downloaded the JavaFX SDK, for example, from [Installing the JavaFX SDK](https://www.oracle.com/java/technologies/install-javafx-sdk.html).
2. Verify that your compiler settings are compatible (go to File > Settings > Build, Execution, Deployment > Compiler).

![New Project](/Images/jfx14.JPG)

4. In Project Structure, add the appropriate libraries and dependencies to your module settings.
5. Configure the VM options under Run > Edit Configurations. Refer to the figure below for guidance.

![New Project](/Images/jfx13.JPG)

