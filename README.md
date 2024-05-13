JavascriptExecutor js = (JavascriptExecutor) driver;
WebElement lastEntry = driver.findElement(By.xpath("your_xpath_here")); // Update this XPath to correctly identify the last entry.

// Ensure the element type matches what's needed in the XML/HTML structure.
String script = "var newElement = document.createElement('string');" +  // Assume 'string' is a valid element, change it if needed.
                "newElement.textContent = 'New String Here';" +  // Use textContent for plain text.
                "arguments[0].parentNode.appendChild(newElement);";  // Append to the parent of the last entry.

js.executeScript(script, lastEntry);

