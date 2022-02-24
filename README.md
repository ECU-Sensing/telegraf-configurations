# telegraf-configurations

## Industry Standards to be adhered to here:
    1. Seperation of Configuration Files
        - Sensor Inputs
        - InfluxDB Output (This is likley mostly static)
        - Performance Inputs
    2. Adding Alias to Plugins
        - alias = 'InfluxDB Output'
    3. Tag fields
        - this is beneficial to users (readable names)
        - prevents data from mistakenly being overwritten 
    4. Use routing to keep sensor, performance, etc data in seperate locations of output
        - namepass = only accept metrics whose name matches pattern
        - namedrop = drop metrics whose name matches pattern
        - bucket_tag = helps drop mutiple inputs into seperate buckets on InfluxDB (define at top along with bucket="" within inputs)
    5. Pass Instance specific information for output as env variables 
       - Examples of this are influx_host, influx_token, influx_org, influx_bucket, etc.
    6. Enable debugging
    7. Monitor Telegraf
    8. Split Configurations to multiple contatiners (see docker-compose-example.yml)

![Example](https://github.com/ECU-Sensing/telegraf-configurations/blob/main/example.PNG)