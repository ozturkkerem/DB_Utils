# DB_Utils
var newElement = document.createElement('div');
newElement.innerHTML = '<String>New String Here</String>';
if (targetElement.nextSibling) {
    targetElement.parentNode.insertBefore(newElement.firstChild, targetElement.nextSibling);
} else {
    targetElement.parentNode.appendChild(newElement.firstChild);
}

JavascriptExecutor js = (JavascriptExecutor) driver;
WebElement lastEntry = driver.findElement(By.xpath("//String[contains(text(), 'Your Last String')]"));  // Adjust this to target the last string you added

String script = "var targetElement = arguments[0];" +
                "var newElement = document.createElement('div');" +
                "newElement.innerHTML = '<String>New String Here</String>';" +
                "if (targetElement.nextSibling) {" +
                "    targetElement.parentNode.insertBefore(newElement.firstChild, targetElement.nextSibling);" +
                "} else {" +
                "    targetElement.parentNode.appendChild(newElement.firstChild);" +
                "}";

js.executeScript(script, lastEntry);

