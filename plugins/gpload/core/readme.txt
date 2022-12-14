% 参照生成以下文件
---
VERSION: 1.0.0.1

DATABASE: gdzq_dc
USER: gpadmin
HOST: 10.84.135.45
PORT: 5432
GPLOAD:
   INPUT:
     - SOURCE:
        FILE:
          - /u02/informatica/10.4.1/server/infa_shared/Temp/staging_jzjy_ks_allseats_0_pipe0
     - COLUMNS:
       - "market_code":
       - "seat_no":
       - "company_name":
       - "seat_type":
       - "ztg_flag":
       - "send_date":
       - "spare":
     - MAX_LINE_LENGTH: 32768
     - FORMAT: CSV
     - DELIMITER: "\x01"
     - ESCAPE: '\'
     - NULL_AS: '\N'
     - QUOTE: '"'
     - ENCODING: 'utf8'
     - ERROR_LIMIT: 0
     - ERROR_TABLE:
   OUTPUT:
     - TABLE: staging.jzjy_ks_allseats
     - MODE: INSERT
   PRELOAD:
     - TRUNCATE: True