This documentation helps in understanding the use of each and every UI test. 

Here are some of the guidelines that are to be followed while creating new test:

Here are some things to put down for guidelines for writing UI (and API) tests: 

 Each UI test method should have no dependencies on any other UI tests. Each test stands alone and does its own init and cleanup. 

When creating UI test classes, derive from UiTestBase 

Specifies the Trait and Collection attributes. Do not specify these attributes on the class itself.  

Provides common properties and methods useful for writing UI test code (e.g., WebDriver property) 

Use the plural form for the test class name 

E.g., UiTests instead of UiTest 

Use Pascal-case for all class names, file names, and public element names 

E.g., UiTests instead of UITests 

Ensure the namespace name reflects the folder path 

E.g., UI tests should be in the Mmm.Iot.FunctionalTests.UiTests namespace 

Perform post-processing on C# code produced by Selenium IDE 

Use this.WebDriver.Value 

Replace all waits with this.DefaultWait, unless a different wait time/behavior is needed, in which case define the new wait as a variable in the test method or class so that it can be reused in place of instantiating new wait objects all over the place 

Omit unnecessary statements/actions (e.g., clicks). Aim to use the fewest possible number of statements/actions to successfully automate the browser for the task at hand. 

Modify any selectors to omit any/all text visible to end-users. No button names, link names, etc. should be used in selectors because those things are likely to change and break tests if used in selectors. 

Evaluate selectors to see if the HTML id attribute can be used. If the element being selected does not have an ID attribute, can one be added? If id is unavailable, consider whether name or class attributes are unique and robust enough. 

Shorten all XPath selectors and/or CSS selectors to omit unnecessary components. Shorter selectors are more robust and more likely to survive changes to the page structure. 

Call this.WebDriver.Value.Close(); at the end of the test 

Save one or more screenshots by calling this.SaveScreenshot 

For the screenshot name, use the name of the test as obtained by the use of the nameof operator 

When saving multiple screenshots, use the name of the test from nameof concatenated with a hyphen and a short distinguishing phrase or identifier 

E.g., this.SaveScreenshot($"{nameof(TenantSwitchingTest)}-BeforeSwitch"); 

To generate random strings or numbers, use the TestStack.Dossier library and its AnonymousValueFixture class 