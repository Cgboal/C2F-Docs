# Web Interface

Whilst the C2F web interface should be reasonably self explanatory, this section will give an overview of each major feature. The features listed correspond to the navigation elements found on the left hand side of the web interface.

### Homepage

Currently, the homepage is mostly full of remnants from the Bootstrap template used, further down the line, the Dashboard will contain useful information and analytics.

### Reports

The reports dropdown allows you to view the data which has been reported by modules. The report data can be displayed revolving around either Groups, Agents, or Modules. 

#### Report Types

* Group Reports display the data reported by all Agents within a group sorted by Module. 
* Agent Reports display the data reported by the selected Agent sorted by Module.
* Module Reports display all data reported by Agents corresponding to the selected module. The reports are sorted by both Group, and Agents.

{% hint style="info" %}
Module Reports are not currently implemented, additionally, there may be some bugs relating to the accordions on the Report pages
{% endhint %}

### Groups

The groups dropdown allows you to both create new groups, and view existing groups. Groups are collections of Agents and Modules. When viewing a Group, you can select "Run all" in the top right to have Agents within the group run all Modules assigned to the group. Groups can be comprised of any number of Agents, and Agents can be in any number of Groups.   

### Agents

The Agents dropdown allows you to access information about each Agent. Agent online/offline status, and logs can be viewed here. Additionally, information on assigned modules will be displayed displayed here.  

### Modules

The Modules dropdown allows you to upload and assimilate new Modules, and view information pertaining to each Module. The format of Module files will be discussed in the Creating Modules section.

{% hint style="info" %}
When assimilating new modules, momentary downtime will occur as database migrations are occurring. Refreshing after a few seconds should take you back to the login page.   
{% endhint %}

