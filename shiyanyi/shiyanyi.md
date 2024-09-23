# 《实验一》  
>**学院:省级示范性软件学院**
>
>**题目:**《实验二：索引操作与文档操作练习》
>
>**姓名**: 刘乐
>
>**学号**: 2200770085
>
>**班级**: 软工2204
>
>**日期**: 2024-9-14
>
>**实验环境**: Elasticsearch8.12.2 Kibana8.12.2

##  一、实验目的
1. 掌握Elasticsearch 安装IK分词器安装方法
2. 掌握Elasticsearch 索引操作方法
3. 掌握Elasticsearch 文档操作训练
4. 掌握Elasticsearch 高级查询与DSL训练
##  二、实验内容
###  1. 索引操作练习
- **根据字段描述创建索引**
  - 用户信息索引

        {
          "mappings":{
          "properties":{
            "user_id":{
                "type":"keyword"
            },
            "name":{
                "type":"text"
            },
            "email":{
                "type":"keyword"
            },
            "date_of_birth":{
                "type":"date"
            },
            "gender":{
                "type":"keyword"
            },
            "address":{
                "type":"text"
            },
            "phone_number":{
                "type":"keyword"
            },
            "registration_date":{
                "type":"date"
            },
            "last_login":{
                "type":"date"
            },
            "status":{
                "type":"keyword"
            }
            }
          }   
        }
      ![alt text](image-5.png)
  - 产品目录索引
    
        {
        "mappings":{
            "properties":{
                "product_id":{
                    "type":"keyword"
                },
                "name":{
                    "type":"text"
                },
                "description":{
                    "type":"text"
                },
                "category":{
                    "type":"keyword"
                },
                "price":{
                    "type":"double"
                },
                "stock_quantity":{
                    "type":"integer"
                },
                "supplier":{
                    "type":"keyword"
                },
                "release_date":{
                    "type":"date"
                },
                "tags":{
                    "type":"keyword"
                },
                "rating":{
                    "type":"float"
                }
            }
          }
        }
    ![alt text](image-4.png)
  - 订单记录索引
      
        {
        "mappings":{
            "properties":{
                "order_id":{
                    "type":"keyword"
                },
                "customer_id":{
                    "type":"keyword"
                },
                "order_date":{
                    "type":"date"
                },
                "status":{
                    "type":"keyword"
                },
                "total_amount":{
                    "type":"double"
                },
                "items":{
                    "type":"nested"
                },
                "shipping_address":{
                    "type":"text"
                },
                "shipping_method":{
                    "type":"keyword"
                },
                "payment_method":{
                    "type":"keyword"
                },
                "shipping_date":{
                    "type":"date"
                },
                "delivery_date":{
                    "type":"date"
                }
              }
            }
        }
        
    ![alt text](image-6.png)      
- **修改索引**
  - **添加常用收货shipping_address** (方便用户)

        {
        "properties":{
            "shipping_address":{
                "type":"text"
            }
        }
        }
    ![alt text](image-7.png)
- **删除索引**
![alt text](image-9.png)
![alt text](image-10.png)
- **查看所有**
### 2.文档操作练习
### 3.高级查询&DSL语句练习
##  三、问题及解决方法
- **restful API 的种类与功能混淆**
![alt text](image-1.png)
post 增 delete 删 get 查 **put 改**
在es中创建表要用PUT，修改表也是PUT
- **DSL语法错误**
  - 不能用"mapping"，要用 **"mappings"**
    ![alt text](image-3.png)
  - 修改索引要**/索引名/_mapping
  ![alt text](image-8.png)
