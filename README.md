# CodepathCyberSecWeek7

Time spent: **4.5** hours spent in total

> Objective: Find, analyze, recreate, and document vulnerabilities affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary: Produces a pop-up when you reload the page.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: <img src="https://github.com/dhruvp5/CodepathCyberSecWeek7/blob/master/Asg7_1.gif?raw=true" alt="gif">
  - [X] Steps to recreate: To recreate this exploit, you need to go to a page or post that has comments enabled on it.  Now, in the comment box, copy and paste the following code line: <script>while(1){alert(document.cookie);}</script>.  This will bring up a popup box that will not go away.
  - [X] Affected source code:
    - [Link 1](https://compsecurityconcepts.wordpress.com/tag/cross-site-scripting/)
2. (Required) WordPress <= 4.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary: Creates a pop up when you hover the link on the post.
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.2.3
  - [X] GIF Walkthrough: <img src="https://github.com/dhruvp5/CodepathCyberSecWeek7/blob/master/Asg7_2.gif?raw=true" alt="gif">
  - [X] Steps to recreate: To recreate this exploit, go to Wordpress dashboard and create a new post.  For the title and the plain text of the post, copy and paste the following code: `" <a href="</a><a title=" onmouseover=alert('test') ">link</a> ""`
  - [X] Affected source code:
    - [Link 2](https://github.com/WordPress/WordPress/blob/master/wp-includes/shortcodes.php)
3. (Required) Cross Site Scripting in Update Plugin
  - [X] Summary: Produces a pop-up when clicking the plugin name.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7
  - [X] GIF Walkthrough: <img src="https://github.com/dhruvp5/CodepathCyberSecWeek7/blob/master/Asg7_3.gif?raw=true" alt="gif">
  - [X] Steps to recreate: Edit a plugins name to `<script>alert("XSS");</script>`. When the update plugin is openede, the XSS exploit will run the script, which could be manipulated to produce malicious output.
  - [X] Affected source code:
    - [Link 3](https://core.trac.wordpress.org/browser/trunk/src/wp-includes/shortcodes.php)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [Dhruv Patel]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
