##Configuring your Sailor Application

You will find Sailor's config file under `conf/conf.lua`. This file contains a table with config strings for core Sailor control, database server configuration and SMTP server configuration for mailer module.

###`sailor.app_name`
Used as a default title tag for your pages and can be invoked at any time from the rest of your app accessing the conf table.

###`sailor.default_static`
Is about flow control. If defined, Sailor will render a specific view as defined, disabling routing. It's useful, for example, for serving a very simple page instead of a complex app or for loading a temporary maintenance page.

###`sailor.default_controller` and `default_action`
Will define which action from which controller will run by default, when no route is called, a.k.a. your index.

###`sailor.theme`
Will define the basic and default theme used for all pages. Sailor is integrated with [Twitter Bootstrap](http://getbootstrap.com) for an enhanced feel. You can add more themes on `/themes` and set a default here. Themes can be changed for specific pages by setting `page.theme` to something else on controller before rendering pages. It can be deactivated by setting it to nil.

###`sailor.layout`
Will define the basic and default layout used for all pages. A layout is the exact .lp file inside your theme folder that will be rendered. For example, one theme can come with many possible different layouts, like front and 'inside' pages, or 1-column and 2-columns. Layout can be changed for specific pages by setting `page.layout` to something else on controller before rendering pages. It can be deactivated by setting it to nil.

###`sailor.route_parameter`
Is for page routing when friendly urls are deactivated, which is done accessing a get variable, the default is 'r', but you can change it here if you wish.

###`sailor.default_error404`
Sets a default view for 404 errors. It can be deactivated by setting it to nil.

###`sailor.enable_autogen`
Turns Sailor's autogen on or off by setting it to true or false. The autogen is a tool to autogenerate models and CRUDs. You can find more about it under the Autogen section. The default value is false for avoiding accidental overwriting of files.

###`sailor.friendly_urls`
turns friendly urls on or off by setting it to true or false. Normally, to access the view action of the article controller passing 4 as id via get variables, you would have to type in your address bar `http://your_url.com/?r=article/view&id=4`. However, when friendly urls are set to true, you can access it on `http://your_url.com/article/view/id/4` which is way cleaner. If you want to personalize it, for Xavante, you need to edit /start-server.lua and for Apache2, .htaccess.

###`sailor.max_upload`
Sets, in bytes, the max size of files to be uploaded using file inputs on forms.

###`environment`
Is a string with the name of your current environment. Example: 'test'.

###`hide_stack_trace`
Is a boolean that if set to true will make Sailor not throw the full stack trace on errors but a default 500 Internal Server Error message.

###`db`
Contains a table with your different database setups. They must contain the following fields:

####`driver`
Is your database driver, example: 'mysql'.
    
####`host`
Is your database host, example: 'localhost'.

####`user` and `db.pass`
Are the login information for your database.

####`dbname`
Is the database name. You can leave db configs blank if you are not persisting models.

###`smtp.server`
Is the server for sending emails. You can leave smtp configs blank if you are not using your application for sending emails.

###`smtp.user` and `smtp.server`
Are the login information for your smtp server.

###`smtp.from`
Is the email address who is sending emails.

###`lua_at_client.vm`
Is the virtual machine that will translate Lua to Javascript in case you'd like to write Lua code for the browser as well. `starlight` is the default. Other options are `moonshine`, `lua51js` and `luavmjs`. You can find more details about them on the reference manual.

###`debug.inspect`
Toggles on/off the exhibition of debug messages on the bottom of the page made with `page.inspect`.

