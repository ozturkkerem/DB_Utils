# DB_Utils
JavascriptExecutor js = (JavascriptExecutor) driver;
WebElement lastEntry = driver.findElement(By.xpath("your_xpath_here")); // Replace "your_xpath_here" with the actual XPath to the last entry.

String script = "var newElement = document.createElement('div');" +  // Create a new 'div' or other appropriate element.
                "newElement.innerHTML = 'New String Here';" +          // Set the content of the new element.
                "arguments[0].parentNode.appendChild(newElement);";    // Append the new element as the last child of the parent node.

js.executeScript(script, lastEntry);


String script = "var newElement = document.createElement('div');" +
                "newElement.innerHTML = 'New String Here';" +
                "var parent = arguments[0].parentNode;" +
                "parent.insertBefore(newElement, arguments[0].nextSibling);";  // This will insert right after the lastEntry

js.executeScript(script, lastEntry);

