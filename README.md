# DB_Utils

// Script to create a new 'String' XML element below the last one
String newXmlLine = "<String>New String Here</String>";  // Adjust this line to match the XML structure you need
String script = "var newElement = document.createElement('div');" +
                "newElement.innerHTML = '" + newXmlLine + "';" +
                "arguments[0].parentNode.insertBefore(newElement.firstChild, arguments[0].nextSibling.nextSibling);";

js.executeScript(script, lastEntry);
