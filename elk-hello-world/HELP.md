# Getting Started

### Reference Documentation

```
.\bin\logstash.bat -f .\config\logstash-simple.conf
```


curl http://localhost:9898/getUser/2


test  elasticsearch 
 
the current indexes 
http://localhost:9200/_cat/indices

Get active index (find by timestamp)
yellow open logstash-2021.04.29-000001      28p_2MheSKCVHIEAAmJFPg 1 1 31    0  64.6kb  64.6kb

Give index 
http://localhost:9200/logstash-2021.04.29-000001


https://www.youtube.com/watch?v=5s9pR9UUtAU




Local file loging 


input {
  file {
    type => "some_access_log"
    path => [ "/var/log/vs01/*.log", "/var/log/vs02/*.log" ]
    exclude => [ "*.gz", "*.zip", "*.rar" ]
    start_position => "end"
    stat_interval => 1
    discover_interval => 30
  }

---------------------------

step2 

logstash-2021.04.29-000001

curl http://localhost:9898/elk/exception

 ----------------------------
filter {
  #If log line contains tab character followed by 'at' then we will tag that entry as stacktrace
  if [message] =~ "\tat" {
    grok {
      match => ["message", "^(\tat)"]
      add_tag => ["stacktrace"]
    }
  }
 
}
 