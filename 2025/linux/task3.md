# Log File Analysis with AWK, Grep & Sed
## Use grep to find all occurrences of the word "error".
#### **Task:**

- Download the **Linux_2k.log** file.

  **Solution:**
  - In GitHub, right-click the **Raw** button and copy the link address.
  - Use `wget` to download the file.

wget https://github.com/logpai/loghub/raw/refs/heads/master/Linux/Linux_2k.log

- Extract insights using commands:
  - Use `grep` to find all occurrences of **"error"**.
    
    **Solution**
   
    grep -i "error" Linux_2k.log

    **Output**: No occurrence found.
  - Use `awk` to extract **timestamps and log levels**.
  
    **Solution:**

    Jun 14 15:16:01 ERROR
    Jun 14 15:16:02 INFO
    Jun 14 15:16:02 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    Jun 15 02:04:59 ERROR
    .
    .
 

  - Use `sed` to replace all IP addresses with **[REDACTED]**.

    **Solution**
   
    sed 's \([[:digit:]]\+\(\.\|-\)\)\{3\}[[:digit:]]\+ [REDACTED] g' < Linux_2k.log
    #Output:
     211.72.151.162 --> [REDACTED]
     65-0-87-32 --> [REDACTED]
    ```
  
    Jul 17 23:21:54 combo ftpd[25232]: connection from [REDACTED] ([REDACTED].dsl.in-addr.zen.co.uk) at Sun Jul 17 23:21:54 2005
    Jul 17 23:21:54 combo ftpd[25233]: connection from [REDACTED] ([REDACTED].dsl.in-addr.zen.co.uk) at Sun Jul 17 23:21:54 2005
    Jul 17 23:21:54 combo ftpd[25234]: connection from [REDACTED] ([REDACTED].dsl.in-addr.zen.co.uk) at Sun Jul 17 23:21:54 2005
    Jul 17 23:21:54 combo ftpd[25235]: connection from [REDACTED] ([REDACTED].dsl.in-addr.zen.co.uk) at Sun Jul 17 23:21:54 2005
    Jul 17 23:21:54 combo ftpd[25236]: connection from [REDACTED] ([REDACTED].dsl.in-addr.zen.co.uk) at Sun Jul 17 23:21:54 2005

    ```

---
