# RESTful microPoS 


请参考spring-petclinic-rest/spring-petclinic-microserivces 将aw04的webpos项目改为rest风格的微服务架构
（至少包含产品管理服务pos-products和购物车管理服务pos-carts以及discovery/gateway等微服务架构下需要的基础设施服务）。具体要求包括：

1. 请使用OpenAPI的定义每个服务的rest接口（参考pos-products）
2. 请使用ehcache管理缓存；
3. 请注意使用断路器等机制；
4. 有兴趣的同学可自学一些reactjs或vuejs等为microPoS开发一个前端。

## pos-discovery

a eureka discovery server, running on localhost:8761

## pos-products

product server, running on localhost:8081

use ehcache on `JDRepository.allProducts`

## pos-cart

cart server, running on localhost:8083

use circuitbreaker on `CartServiceImple.getProduct`: when getting product list from product server failed, return a pre-prepared product list

## pos-gateway

gateway, running on localhost:8080

route for product service and cart service