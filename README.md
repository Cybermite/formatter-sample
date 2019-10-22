# formatter-sample
Sample project to demostrate formatter-maven-plugin issue when formatting or validating a formatted file that has line endings that do not match the current system's line endings. For example, the file has LF when building on windows.

Steps:
1. Verify that the App.java file has LF line endings if on windows. If on linux or mac, verify the line endings are CRLF.
2. Run `mvn clean verify`
3. The build will fail because App.java was not "formatted". If we run `mvn formatter:format`, it will format the file but will only change the line endings. The plugin is configured to keep the existing line endings within the file, so this is not expected.
