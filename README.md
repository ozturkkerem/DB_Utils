WebElement lastEntry = driver.findElement(By.xpath("//entry[last()]")); // Adjust this XPath to accurately target the last <entry> node or the specific point of insertion.

// Prepare the new entry XML string.
String newEntryXml = "<entry key='newKey'>New String Here</entry>"; // Adjust 'newKey' and 'New String Here' as needed.

// JavaScript to create a new node and insert it after the last entry.
String script = "var parser = new DOMParser();" +
                "var newDoc = parser.parseFromString('" + newEntryXml + "', 'application/xml');" +
                "var newEntry = document.importNode(newDoc.documentElement, true);" +
                "arguments[0].parentNode.appendChild(newEntry);";  // This appends the new entry after the last entry within the same parent.

js.executeScript(script, lastEntry);

