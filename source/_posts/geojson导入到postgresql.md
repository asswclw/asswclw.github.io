---
title: geojson文件导入PostgreSQL数据库
---
方法有两个:
1. 使用QGIS的数据库导入工具
2. 使用ogr2ogr命令<br>
  `ogr2ogr -f "PostgreSQL" PG:"host=xxx port=xxx dbname=xxx user=xxx password=xxx" source.geojson -nln schema.tabel -progress -append`<br>
  其中部分参数含义如下:
   - host: 数据库实例所在地址
   - port: 数据库实例端口
   - dbname: 数据库名称
   - user: 用户名称
   - password: 密码
   - source.geojson,源文件,后缀也可以为json, ogr自己会识别
   - nln, new layer name, 数据库中的表名,参数值最好带上具体的schema名称
   - progress, 数据导入进度,数据量大时切记加上
   - append, 增量导入<br>
更多参数可以参考[ogr2ogr官网](http://www.gdal.org/ogr2ogr.html)