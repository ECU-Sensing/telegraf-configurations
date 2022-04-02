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
    4. Use routing to keep sensor, performance, etc data in separate locations of output
        - namepass = only accept metrics whose name matches pattern
        - namedrop = drop metrics whose name matches pattern
        - bucket_tag = helps drop multiple inputs into separate buckets on InfluxDB (define at top along with bucket="" within inputs)
    5. Pass Instance specific information for output as env variables 
       - Examples of this are influx_host, influx_token, influx_org, influx_bucket, etc.
    6. Enable debugging
    7. Monitor Telegraf
    8. Split Configurations to multiple containers (see docker-compose-example.yml)

    More Information: https://www.influxdata.com/blog/telegraf-best-practices/ 

![Example](https://github.com/ECU-Sensing/telegraf-configurations/blob/main/example.PNG)