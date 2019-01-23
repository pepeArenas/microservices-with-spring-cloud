we have the following structure on our git bases config server
application.properties(in root as default)
station1
  s1rates.properties
  s1rates-dev.properties
  s1rates-qa.properties
station2
  s2rates.properties
  s2rates-dev.properties

This is what we are going to have if search for the followings urls
http://localhost:8888/s1rates/default
    -application.properties
    -s1rates.properties
http://localhost:8888/s2rates/qa --- this qa profile not exist so it will return just the default
    -application.properties
http://localhost:8888/s3rates/default --- there is no s3 sub folder
    -application.properties
http://localhost:8888/s1rates/dev
    -application.properties
    -s1rates.properties
    -s1rates-dev.properties

Also we can acces to a particular resource as a different formats, for example
http://localhost:8888/s1rates-default.properties---it will give me the configuration as a .properties format
http://localhost:8888/s1rates-default.yml it will give me the .yml format of the configuration
http://localhost:8888/s1rates-default.json it will give me the .json format of the configuration

Where -default is the profile, we can specify a profile an it will return us and if we specify a profile that do not exists, then it will return us the default in this case the one its in the root (application.properties)
