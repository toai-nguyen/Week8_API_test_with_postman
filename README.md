# Week8_API_test_with_postman

# Báo cáo kiểm thử API

Ngày kiểm thử: 19/06/2025

Người kiểm thử: Nguyễn Thế Toại


1. Mục tiêu kiểm thử: Sử dụng Postman để kiểm thử API thực tế
2. Môi trường kiểm thử: Postman
3. PHương pháp kiểm thử: Kiểm thử tự động và thủ công trên phần mềm Postman

## 1.Tên Kịch Bản: Kiểm thử cơ bản của 1 URL
*  Mục Đích: Test khả năng hoạt động của URL và phần mềm Postman
*  Phương Thức HTTP (GET/POST/PUT/DELETE): GET
*  URL: https://api.restful-api.dev/objects
*  Kết Quả Mong Đợi: Gửi yêu cầu thành công
*  Kết Quả Thực Tế: Server phản hồi 200, gọi dữ liệu thành công
*  Trạng Thái: Thành công
*  Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/451ebfa6-1684-450c-b24f-8cca13315cec)
* Kết quả kiểm thử chi tiết
```
[
    {
        "id": "1",
        "name": "Google Pixel 6 Pro",
        "data": {
            "color": "Cloudy White",
            "capacity": "128 GB"
        }
    },
    {
        "id": "2",
        "name": "Apple iPhone 12 Mini, 256GB, Blue",
        "data": null
    },
    {
        "id": "3",
        "name": "Apple iPhone 12 Pro Max",
        "data": {
            "color": "Cloudy White",
            "capacity GB": 512
        }
    },
    {
        "id": "4",
        "name": "Apple iPhone 11, 64GB",
        "data": {
            "price": 389.99,
            "color": "Purple"
        }
    },
    {
        "id": "5",
        "name": "Samsung Galaxy Z Fold2",
        "data": {
            "price": 689.99,
            "color": "Brown"
        }
    },
    {
        "id": "6",
        "name": "Apple AirPods",
        "data": {
            "generation": "3rd",
            "price": 120
        }
    },
    {
        "id": "7",
        "name": "Apple MacBook Pro 16",
        "data": {
            "year": 2019,
            "price": 1849.99,
            "CPU model": "Intel Core i9",
            "Hard disk size": "1 TB"
        }
    },
    {
        "id": "8",
        "name": "Apple Watch Series 8",
        "data": {
            "Strap Colour": "Elderberry",
            "Case Size": "41mm"
        }
    },
    {
        "id": "9",
        "name": "Beats Studio3 Wireless",
        "data": {
            "Color": "Red",
            "Description": "High-performance wireless noise cancelling headphones"
        }
    },
    {
        "id": "10",
        "name": "Apple iPad Mini 5th Gen",
        "data": {
            "Capacity": "64 GB",
            "Screen size": 7.9
        }
    },
    {
        "id": "11",
        "name": "Apple iPad Mini 5th Gen",
        "data": {
            "Capacity": "254 GB",
            "Screen size": 7.9
        }
    },
    {
        "id": "12",
        "name": "Apple iPad Air",
        "data": {
            "Generation": "4th",
            "Price": "419.99",
            "Capacity": "64 GB"
        }
    },
    {
        "id": "13",
        "name": "Apple iPad Air",
        "data": {
            "Generation": "4th",
            "Price": "519.99",
            "Capacity": "256 GB"
        }
    }
]
```
## 2. Kịch bản kiểm thử luồng GET ListOfObjectById
* Kiểm thử cơ bản một API với nhiều tham số
* Mục đích: Kiểm tra luông ListOfObjectById của API
* Phương thức: GET
* URL: https://api.restful-api.dev/objects?id=3&id=5&id=100
* Kết quả mong đợi: Gửi yêu cầu thành công, trả về 3 object tương ứng với 3 id nhập vào
* Kết quả thực tế: Chỉ gửi về hai object có id 3 và 5 (có thể id 100 không có hoặc không tồn tại trong database)
* Kết quả kiểm thử
![image](https://github.com/user-attachments/assets/39daa99a-06ab-4b7c-80df-957eda5d0a08)
* Dữ liệu trả về:
```
[
    {
        "id": "3",
        "name": "Apple iPhone 12 Pro Max",
        "data": {
            "color": "Cloudy White",
            "capacity GB": 512
        }
    },
    {
        "id": "5",
        "name": "Samsung Galaxy Z Fold2",
        "data": {
            "price": 689.99,
            "color": "Brown"
        }
    }
]
```
## 3. Kiểm thử GET byID (getById)
* Kiểm thử cơ bản một API với nhiều tham số
* Mục đích: Kiểm tra luồng getById của API
* Phương thức: GET
* URL: https://api.restful-api.dev/objects/7
* Kết quả mong đợi: Gửi yêu cầu thành công, trả về object tương ứng với id nhập vào
* Kết quả thực tế: Server phản hồi với status 200 (trả về thông tin thành công)
* Kết quả kiểm thử:
![image](https://github.com/user-attachments/assets/2065588c-df29-4e01-973e-a39e72705e16)
* Dữ liệu trả về
```
{
    "id": "7",
    "name": "Apple MacBook Pro 16",
    "data": {
        "year": 2019,
        "price": 1849.99,
        "CPU model": "Intel Core i9",
        "Hard disk size": "1 TB"
    }
}
```
## 4. Kiểm thử POST (Add object)
* Kiểm thử thêm đối tượng thông qua luồng POST
* Mục đích: Kiểm tra luồng post của API
* Phương thức: POST
* URL: https://api.restful-api.dev/objects
* Payload:
```
  {
   "name": "Apple MacBook Pro 16",
   "data": {
      "year": 2019,
      "price": 1849.99,
      "CPU model": "Intel Core i9",
      "Hard disk size": "1 TB"
   }
}
  ```
* Kết quả mong đợi: Thêm đối tượng thành công,
* Kết quả thực tế: Server phản hồi code 200 nhưng chỉ thông báo chứ không trả về đối tượng đã thêm
![image](https://github.com/user-attachments/assets/ddab82ec-ea78-4114-aa1c-522911873c74)
## 5. Kết luận
* Thứ nhất, các luồng cơ bản của API đều hoạt động và phản hồi khi được gọi (GET,POST)
* Thứ hai, luồng POST phản hồi nhưng không đáng tin (không trả về kết quả)
* Số lần test 4
* Done: 3
* Fail: 1
