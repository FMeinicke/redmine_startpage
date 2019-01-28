# Redmine Startpage Plugin
--- 
This is a plugin for Redmine.  It allows the admin to select almost any redmine sub page as landing page after a user logged in.
This project was forked from txinto's [redmine_startpage](https://github.com/txinto/redmine_startpage) plugin. I simply added the option to also specify a project. The plugin was tested with Redmine 3.4.6.stable.

## Installation  
```
cd {redmine_root}/plugins
git clone https://github.com/FlorianMeinicke/redmine_startpage.git
```
After that just restart Redmine and your good to go.

Please note that the plugin directory must be 'redmine_startpage'.  
Github adds suffixes to the downloaded file so if you extract it directly to the plugin directory you will need to rename it to `redmine_startpage`.


## Examples
If the starting page must be the initial wiki page (the topic named 'wiki') for the 'redminewikistartpage' project, then

Redmine 1.x
```
    Project: <empty>
    Controller: projects
    Action: redminewikistartpage
    Id: wiki
    Extra argument name must be an empty string.
    Extra argument value must be an empty string.
```
Redmine 2.x and higher
```
    Project: <empty>
    Controller: wiki (name of the controller)
    Action: show
    Id: wiki (name of the topic to show)
    Extra argument name: project_id
    Extra argument value: redminewikistartpage
```
If the starting page should be the issues overview page of the project named 'Sample Project' (and therefore with a project id of 'sample_project') then
```
    Project: sample_project
    Controller: issues
    Action: index
    Id: <empty>
    Extra argument name: <empty>
    Extra argument value: <empty>
```
If you also want to specify a user defined query for instance then 
```
    Project: sample_project
    Controller: issues
    Action: index
    Id: <empty>
    Extra argument name: query_id
    Extra argument value: 1 (or any other id you want)
```


Github repository: https://github.com/txinto/redmine_startpage
Homepage: http://gatatac.org/projects/redmine-startpage/wiki

This plugin is published under GPL v2 license.
https://www.gnu.org/licenses/gpl-2.0.html
