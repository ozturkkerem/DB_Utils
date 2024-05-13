
        try {
            WebElement elementToFocus = driver.findElement(By.xpath("your_xpath_here"));  // XPath to your element

            JavascriptExecutor js = (JavascriptExecutor) driver;
            // Force the element to be focused
            js.executeScript("arguments[0].focus();", elementToFocus);
            // Force a click on the element
            js.executeScript("arguments[0].click();", elementToFocus);
            // Create and dispatch an Enter key event
            js.executeScript("var event = new KeyboardEvent('keydown', {'key':'Enter', 'code':'Enter', 'bubbles':true}); arguments[0].dispatchEvent(event);", elementToFocus);

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }
