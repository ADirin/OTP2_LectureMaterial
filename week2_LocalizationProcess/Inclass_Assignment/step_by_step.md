
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
**NOTE** if you are not given the option to generate the methods for the buttons make sure the project package is correct. Docuble check and fix it with package and folder that you application controller is located 
```xml
<VBox ... fx:controller="org.example.demo0.HelloController">

````

3. If you encounter an error for any component, ensure to import the necessary classes.

![New Project](/Images/jfx3.png)

________________________
### Further lecture demos

[Fuel consumption] (https://github.com/ADirin/lectureDemo_vk2_fuelui.git)





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

![New Project](/Images/jfx15.JPG)

4. In Project Structure, add the appropriate libraries and dependencies to your module settings.

![New Project](/Images/jfx14.JPG)

5. Configure the VM options under Run > Edit Configurations. Refer to the figure below for guidance.

![New Project](/Images/jfx13.JPG)

-------------------------------------------------------------------------------------------------------------------
### Further Lecture Demo

[Fuel Consumption](https://github.com/ADirin/lectureDemo_vk2_fuelui.git)

# Fuel Consumption Calculator in JavaFX

This document provides step-by-step instructions to create a JavaFX application that calculates fuel consumption in a car. The application supports multiple languages (English, French, Japanese, and Persian).

## Prerequisites

- Java Development Kit (JDK) 21 or later
- JavaFX SDK
- An IDE (e.g., IntelliJ IDEA) for Java development

## Project Setup

1. **Create a New JavaFX Project**
   - Open your IDE (e.g., IntelliJ IDEA).
   - Create a new Java project.
   - Ensure you have JavaFX libraries added to your project.

2. **Add JavaFX Libraries**
   - Add the necessary JavaFX libraries to your project.
   - Ensure the following libraries are included:
     - `javafx-controls`
     - `javafx-fxml`
     - `javafx-graphics`

3. **Create the Project Structure**
   - Create a package named `org.example.fuelconsumption`.
   - Create the following files:
     - `HelloApplication.java`
     - `HelloController.java`
     - `hello-view.fxml`
     - `messages_en.properties`
     - `messages_fr.properties`
     - `messages_ja.properties`
     - `messages_fa.properties`

## Code Implementation

### 1. Create the Main Application Class



Create a file named `HelloApplication.java`:

![Fuel Consumption](/Images/fuel.png)


```java
package org.example.fuelconsumption;

import javafx.application.Application;
import javafx.fxml.FXMLLoader;
import javafx.scene.Scene;
import javafx.stage.Stage;

public class HelloApplication extends Application {
    @Override
    public void start(Stage stage) throws Exception {
        FXMLLoader fxmlLoader = new FXMLLoader(HelloApplication.class.getResource("hello-view.fxml"));
        Scene scene = new Scene(fxmlLoader.load(), 300, 300);
        stage.setTitle("Fuel Consumption Calculator");
        stage.setScene(scene);
        stage.show();
    }

    public static void main(String[] args) {
        launch();
    }
}
````
### 2. Create the Controller Class
Create a file named HelloController.java:

```java
package org.example.fuelconsumption;

import javafx.event.ActionEvent;
import javafx.fxml.FXML;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.text.Font;

import java.util.Locale;
import java.util.MissingResourceException;
import java.util.ResourceBundle;

public class HelloController {

    @FXML
    private Label lblDistance;

    @FXML
    private Label lblFuel;

    @FXML
    private TextField txtDistance;

    @FXML
    private TextField txtFuel;

    @FXML
    private Button btnCalculate;

    @FXML
    private Label lblResult;

    private ResourceBundle bundle;

    @FXML
    public void onCalculateClick(ActionEvent actionEvent) {
        try {
            double distance = Double.parseDouble(txtDistance.getText());
            double fuel = Double.parseDouble(txtFuel.getText());
            double consumption = (fuel / distance) * 100;
            lblResult.setText(String.format(bundle.getString("result.label"), String.format("%.2f", consumption)));
        } catch (NumberFormatException e) {
            lblResult.setText(bundle.getString("invalid.input"));
        }
    }

    public void initialize() {
        setLanguage(new Locale("en"));
    }

    public void onENClick(ActionEvent actionEvent) {
        setLanguage(new Locale("en"));
    }

    public void onFRClick(ActionEvent actionEvent) {
        setLanguage(new Locale("fr"));
    }

    public void onJPClick(ActionEvent actionEvent) {
        setLanguage(new Locale("ja"));
    }

    public void onIRClick(ActionEvent actionEvent) {
        setLanguage(new Locale("fa"));
    }

    private void setLanguage(Locale locale) {
        try {
            bundle = ResourceBundle.getBundle("messages", locale);
            lblDistance.setText(bundle.getString("distance.label"));
            lblFuel.setText(bundle.getString("fuel.label"));
            btnCalculate.setText(bundle.getString("calculate.button"));
            lblResult.setText("");
        } catch (MissingResourceException e) {
            e.printStackTrace();
            lblResult.setText("Error loading language resources.");
        }
    }
}

```
### 3. Create the FXML Layout
Create a file named hello-view.fxml:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.geometry.Insets?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.layout.VBox?>
<?import javafx.scene.control.Button?>
<?import javafx.scene.control.TextField?>

<VBox prefHeight="300.0" prefWidth="300.0" spacing="10.0" xmlns="http://javafx.com/javafx/21" xmlns:fx="http://javafx.com/fxml/1" fx:controller="org.example.fuelconsumption.HelloController">
  <padding>
    <Insets bottom="10.0" left="10.0" right="10.0" top="10.0"/>
  </padding>
  <Label fx:id="lblDistance"/>
  <TextField fx:id="txtDistance"/>
  <Label fx:id="lblFuel"/>
  <TextField fx:id="txtFuel"/>
  <Button fx:id="btnCalculate" onAction="#onCalculateClick"/>
  <Label fx:id="lblResult"/>
  <Button text="EN" onAction="#onENClick"/>
  <Button text="FR" onAction="#onFRClick"/>
  <Button text="JP" onAction="#onJPClick"/>
  <Button text="IR" onAction="#onIRClick"/>
</VBox>

```
### 4. Create the Resource Bundles
Create the following properties files:
```css
calculate.button=Calculate
distance.label=Distance (km)
fuel.label=Fuel Used (litres)
result.label=Fuel Consumption: %s L/100km
invalid.input=Please enter valid numbers.

```
```css
calculate.button=Calculer
distance.label=Distance (km)
fuel.label=Carburant Utilisé (litres)
result.label=Consommation de carburant : %s L/100km
invalid.input=Veuillez entrer des chiffres valides.

```
```css
calculate.button=計算する
distance.label=距離 (km)
fuel.label=使用した燃料 (リットル)
result.label=燃料消費量: %s L/100km
invalid.input=有効な数字を入力してください。


```
```css
calculate.button=محاسبه
distance.label=مسافت (کیلومتر)
fuel.label=سوخت مصرفی (لیتر)
result.label=مصرف سوخت: %s L/100km
invalid.input=لطفاً شماره‌های معتبر وارد کنید.


```
## Running the Application
1. Compile the Project: Ensure all files are saved and compile your project.
2. Run the Application: Execute the HelloApplication class.
3. Input Data:
   - Enter the distance in kilometers and the amount of fuel used in liters.
   - Click on the "Calculate" button to see the fuel consumption.
   - Change Language: Click on the language buttons (EN, FR, JP, IR) to switch between languages.
