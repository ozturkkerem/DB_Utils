JavascriptExecutor js = (JavascriptExecutor) driver;
WebElement element = driver.findElement(By.xpath("your_xpath_here"));  // Replace with your actual XPath

// JavaScript to perform a click and then send an Enter key press
String script = 
    "var target = arguments[0];" +
    "target.click();" +  // Simulate mouse click
    "var event = new KeyboardEvent('keydown', {" +
    "    key: 'Enter'," +
    "    code: 'Enter'," +
    "    bubbles: true" +
    "});" +
    "target.dispatchEvent(event);";  // Dispatch the Enter key event

js.executeScript(script, element);


