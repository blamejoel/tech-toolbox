# tech-toolbox
Intranet toolkit made to simplify access to internal resources scattered across
the network by bringing together most commonly used links/resources.  

TODO: Scrub through source code and redact any confidential information from
previous employer before uploading to git.

## Purpose
This "Tech Toolbox" was created to solve the problem of existing and new 
employees not using the appropriate company resources available to expedite
issue resolution due to not knowing where the resources are or even knowing
they exist.

## Design/Build Process
#### Restrictions
* Since the toolbox would contain potentially confidential information, it 
would need to be accessible within the company intranet ONLY. 
* Due to lack of access rights to network servers and settings, the toolbox 
would need to be as "barebones" as possible since server-side interpreter would 
not be an option. All files for the toolkit would be loaded in a browser and 
hosted on company SharePoint server so that http:// access would be possible. 
* The toolbox should have a "clean" or minimilstic design in order to appeal 
to non-tech savvy employees as to not be overwhelming and instead be inviting 
in order to encourage use.

#### Implementation Approach
With the above restrictions in mind, the toolbox was designed from scratch in 
HTML, with some CSS for styling. Eventually, more features were added thanks 
to HTML5 features and Javascript/JQuery. Spoiler alert, it worked!  

#### Features
* Fixed header populated with important resource URLs, some web address, some 
intranet address, some network folder addresses. 
    * JS/JQquery was added to detect the browser being used and present the 
    user with alternate CSS styling and a dialog box on links that were network 
    folders so that they would know the resource was available, and would be 
    more useful if accessed with a browser that would open the resource as a 
    folder in Windows File Explorer. 
* Customizable list of top 5 most "clicked" links unique to each user. - 
JS/JQuery was used to track the "click count" for each link and create a 
dynamic unordered list in the navigation bar sorted by most-clicked. The data 
was saved in browser local storage and a fresh list of most-clicked links was 
generated on each click and/or page load. 
* iframe in the main body of the page featuring an account lookup that was used 
for every issue an employee would be working with. 
* Email template generator forms to provide a consistent email template to be 
used for specific issues that would need to be emailed out to another internal 
email distribution list. The template ensured that every email sent would have 
a consistent format, regardless of the agent that sent it. Having a form with 
minimal fields would reduce the time it took an agent to finish their case by 
instead only asking for a few fields, and then having a script fill in the rest 
and let the user send via the Outlook email client. 
* Signature generator to help new employees create their corporate signature 
that would be attached to all official communication. The generator would 
accept their name, title, email, and phone number and generate an appropriate 
signature that followed the corporate signature guidelines with colors, fonts, 
etc.
* User detection by loading a very light intranet search page behind the 
scenes. The background page was loaded and the HTML was scraped with a 
JS/Jquery script to find the domain user info that would populate in the page. 
The user info was then passed back into the toolbox to be parsed and displayed
along with an image for each user from the corporate directory. User detection
was not used as a security feature, but instead was just a fun, personalized
touch for each user.
