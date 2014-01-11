#UNIX timestamp  

```
#!sql
SELECT round(extract(epoch from now())); 
```

[9.9. Date/Time Functions and Operators  ]: http://www.postgresql.org/docs/8.0/static/functions-datetime.html  

##FUNCTIONS-DATETIME-EXTRACT
EXTRACT, date_part epoch  
For date and timestamp values, the number of seconds since 1970-01-01 00:00:00-00 (can be negative); for interval values, the total number of seconds in the interval  
```
#!sql  
SELECT EXTRACT(EPOCH FROM TIMESTAMP WITH TIME ZONE '2001-02-16 20:38:40-08'); 
```  

`Result: 982384720 `  

Обратно из UNIX в timestamp   

```
#!sql  
SELECT TIMESTAMP WITH TIME ZONE 'epoch' + 982384720 * INTERVAL '1 second';   
```  

`Result: 17.02.2001 12:38:40 <---в местной временной зоне (у меня +08) `  

```
#!sql  
SELECT TIMESTAMP 'epoch' + 982384720 * INTERVAL '1 second';   
```  

`Result: 17.02.2001 04:38:40 <---в UTC `  

