# Các câu lệnh nhanh khi sử dụng với docker

## Sử dụng đẻ tìm kiếm các image bởi name 
- ``docker images "name repo*"``
- Trong đó ký hiệu * nói đến tìm kiếm các image của repo có tên start bằng `name repo`
```
REPOSITORY               TAG                 IMAGE ID            CREATED             SIZE
nginx-ldap-auth-daemon   latest              62614e2b200f        9 months ago        96.2MB
python                   2-alpine            8579e446340f        13 months ago       71.1MB
blackbox-exporter        v0.13.0             cd438996c807        2 years ago         17.5MB
fluentd                  latest              b0cdd0b50e12        2 years ago         136MB
node-exporter            v0.16.0             188af75e2de0        3 years ago         22.9MB
cadvisor                 v0.28.3             75f88e3ec333        3 years ago         62.2MB
```
## Sử dụng để lọc các kết của trong 1 cột
-  ``` awk '{print $3}' ```
- Trong đó ký hiệu ``$3`` là index của cột
- Ví dụ :  ``docker images "name repo*" | awk '{print $3}``
- Ý nghĩa, hiển thị tất cả data của cột thứ 3 -> Image Id
``` 
[dev@vds-alpha-01 ~]$ docker images "*" | awk '{print $3}'
IMAGE
62614e2b200f
8579e446340f
cd438996c807
b0cdd0b50e12
188af75e2de0
75f88e3ec333
```
## Sử dụng xóa nhanh tất cả các image 
- ``` docker images "connection-management*" | awk '{print $3}' |  xargs docker rmi```
- Step
  - Chúng ta sẽ lấy về danh sách của Image bởi name theo pattern
  - Sử dụng awk để lấy về hết Image id
  - Sử dụng xargs để chạy vòng lặp các Image với câu lệnh ``docker rmi`` để xóa Image

