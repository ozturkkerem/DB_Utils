String script = "arguments[0].click();" +
                "var event = new KeyboardEvent('keydown', {'key': 'Enter', 'bubbles': true});" +
                "arguments[0].dispatchEvent(event);";

js.executeScript(script, entry);



