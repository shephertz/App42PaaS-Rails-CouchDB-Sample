App42PaaS-Rails-CouchDB-Sample
==============================

Sample Rails App with CouchDB for App42 PaaS Platform

## Getting Start with App42

1. Setup infrastructure for required environment
2. Create service
3. Deploy a Ruby on Rails application

### Setup infrastructure for required environment

    $ app42 setupInfra   
    
#### Prerequisite production environment configuration

In config/environments/production.rb change

    config.assets.compile = false => config.assets.compile = true

and

    config.serve_static_assets = false => config.serve_static_assets = true

and uncomment below configuration.

    config.action_dispatch.x_sendfile_header = 'X-Accel-Redirect' # for nginx

### Create service

    $ app42 createService
    
DB Configure for Production environment (application_root_dir/config/database.yml) 

    protocol: 'http'                                                 
    host: < host >                  # VM IP  
    port: < port >                  # VM Port  
    prefix: < database name >       # Database Name a/c to prefix and suffix   
    suffix: production              # Database Name a/c to  prefix and suffix  
    username: < user_name >         # User Name  
    password: '< password >'        # Password   
    
### Deploy a Ruby on Rails application

    $ app42 deploy

#### Get application details:

    $ app42 appInfo --app AppName    
    
Visit your application:

