## **Auto-Suggestion Dropdown Demo**

```markdown


This project demonstrates how to interact with an auto-suggestion dropdown using Selenium WebDriver with Java. The example focuses on automating the process of selecting a city from the "From" input field on the MakeMyTrip website.

## Prerequisites

1. Java JDK 8 or higher
2. Maven
3. An IDE (such as IntelliJ IDEA or Eclipse)
4. Firefox browser
5. Git

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/Abdul-Firoz-Khan/AutoSuggestionDropdownDemo.git
    ```
2. Navigate to the project directory:
    ```bash
    cd AutoSuggestionDropdownDemo
    ```
3. Open the project in your preferred IDE.

## Running the Test

1. Make sure you have Firefox installed on your system.
2. Run the `main` method in the `AutoSuggestionDropdownDemo` class.

## Code Explanation

### Package and Imports

```java
package com.afk;

import io.github.bonigarcia.wdm.WebDriverManager;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
```

- **Package Declaration**: The package name is `com.afk`.
- **Imports**: The necessary classes from Selenium WebDriver and WebDriverManager libraries are imported.

### Main Class and Method

```java
/**
 * Auto Suggestion Dropdown Demo
 */
public class AutoSuggestionDropdownDemo {
    public static void main(String[] args) throws InterruptedException {
        // Setup WebDriver using WebDriverManager
        WebDriverManager.firefoxdriver().setup();
        WebDriver driver = new FirefoxDriver();
```

- **Class Declaration**: The main class is `AutoSuggestionDropdownDemo`.
- **Main Method**: The entry point of the program is the `main` method. It throws `InterruptedException` to handle any thread interruptions.

### WebDriver Setup

```java
        // Maximize the browser window
        driver.manage().window().maximize();
```

- **Maximize Window**: The browser window is maximized to ensure all elements are visible.

### Interacting with the Web Page

```java
        try {
            // Navigate to the MakeMyTrip website
            driver.get("https://www.makemytrip.com/");

            // Wait for the page to load
            Thread.sleep(3000);

            // Click on the "From City" label to activate the input field
            driver.findElement(By.xpath("//label[@for='fromCity']")).click();

            // Wait for the input field to become active
            Thread.sleep(3000);

            // Find the "From" input field and enter "Sydney"
            WebElement from = driver.findElement(By.xpath("//input[@placeholder='From']"));
            from.sendKeys("Sydney");

            // Wait for the auto-suggestion dropdown to appear
            Thread.sleep(3000);

            // Navigate through the auto-suggestion dropdown using the arrow down key
            from.sendKeys(Keys.ARROW_DOWN);

            // Wait for the auto-suggestion selection to process
            Thread.sleep(3000);

            // Confirm the selection by pressing the Enter key
            from.sendKeys(Keys.ENTER);
```

- **Navigate to URL**: The WebDriver navigates to the specified URL.
- **Wait for Page Load**: Introduces a delay to ensure the page is fully loaded.
- **Activate Input Field**: Clicks on the "From City" label to activate the input field.
- **Enter City Name**: Finds the "From" input field and enters "Sydney".
- **Handle Auto-Suggestion Dropdown**: Waits for the dropdown to appear, navigates through the suggestions using the arrow down key, and confirms the selection by pressing the Enter key.

### Cleanup

```java
        } finally {
            // Wait for a few seconds before closing the browser
            Thread.sleep(4000);

            // Close the browser
            driver.quit();
        }
    }
}
```

- **Finally Block**: Ensures that the browser is closed after a 4-second wait, even if an exception occurs.

## Additional Information

- This project uses WebDriverManager to manage the browser driver binaries automatically.
- The `Thread.sleep` calls are used to introduce delays for demonstration purposes. In a real-world scenario, you should rely on WebDriverWait or other synchronization methods.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

Feel free to adjust any part of this `README.md` file according to your preferences or additional project details.
