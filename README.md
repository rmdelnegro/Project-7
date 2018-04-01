# Project 7 - WordPress Pentesting

Time spent: **8** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: Embed xss alert in youtube url
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![](https://github.com/rmdelnegro/Project-7/blob/master/youtube_xss.gif)
  - [ ] Steps to recreate: As an editor place an embedded link to a youtube url on one of the pages. Inside the link place an XSS alert. The embedded link is handled incorrectly on load, so whenever the page is accessed the alert will pop up. 
  - [ ] Affected source code:
    - [Link 1](https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/)
    - [Link 2](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    - [Link 3](youtube./12345\)
    - [Link 4](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6817)
2. (Required) Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: Place xss alert in post
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: ![](https://github.com/rmdelnegro/Project-7/blob/master/Img_xss.gif)
  - [ ] Steps to recreate: As an editor, create a new post and attempt to add code for an image in the text area. The code should contain an xss alert such as:
	<IMG SRC=1 ONERROR=alert('XSS')/>
The editor can then post for review by the admin. When the admin previews the post the image will throw an error and send out the alert. 
  - [ ] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/8111)
    - [Link 2](https://wordpress.org/news/2015/07/wordpress-4-2-3/)
    - [Link 3](https://twitter.com/klikkioy/status/624264122570526720) 
    - [Link 4](https://klikki.fi/adv/wordpress3.html)
    - [Link 5](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)
    - [Link 6](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5623)
3. (Required) Unauthenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: Place xss alert inside a comment
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![](https://github.com/rmdelnegro/Project-7/blob/master/comment.gif)
  - [ ] Steps to recreate: log out of all accounts. As a guest on the website enter a comment with an xss alert at the top. Add at least 64kb of ‘A’ characters at the end of the command to max out the length of the comment that can be handled. The website will attempt to truncate the comment and it will be handled improperly, allowing the xss alert to be allowed. 
  - [ ] Affected source code:
    - [Link 1]( https://wpvulndb.com/vulnerabilities/7945)
    - [Link 2](http://klikki.fi/adv/wordpress2.html)
    - [Link 3](http://packetstormsecurity.com/files/131644/)
    - [Link 4](https://www.exploit-db.com/exploits/36844/)


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
