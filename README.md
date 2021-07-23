# MiniELK

## 目录结构
```
├── README.md                   # 说明文档
├── docker-compose.yml          # docker-compose  
├── logstash                    # logstash相关配置
│   └── pipeline
│       ├── logstash.conf       # 配置logstash的input和output
│       └── test_file.log       # 测试数据      
└── .env                        # 环境变量
```

## 使用
1. 启动
    ```shell
    docker-compose up -d
    ```
2. 访问
    - [es](http://localhst:9200)
    - [kibana](http://localhst:5601)
3. 查看数据
    在[kibana-dev_tool](http://localhost:5601/app/dev_tools)写查询语句:
    ```shell
    GET test-logstash-*/_search
    ```
4. 测试
    ```shell
    echo "abcd" >> logstash/pipeline/test_file.log
    ```
    可以看到`test-logstash-*`索引有新数据进来
5. 停止服务
    ```shell
    docker-compose down
    ```

## 更多资料
1. [多节点es](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)
1. [logstsah-input](https://www.elastic.co/guide/en/logstash/current/input-plugins.html)
1. [logstsah-output](https://www.elastic.co/guide/en/logstash/current/output-plugins.html)
1. [kibana-dashboard](https://www.elastic.co/guide/en/kibana/current/dashboard.html)
