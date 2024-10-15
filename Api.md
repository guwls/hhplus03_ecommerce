### API 명세
---
## 잔액 충전 API
```
POST /api/v1/users/{userId}/balance
```
> 200 OK
{
"userId": "user123",
"balance": 50000
}

> 400 Bad Request
{
"error": "잔액충전 실패"
}
---
## 잔액 조회 API
``` 
GET /api/v1/users/balance/{userId}
```
> 200 OK
{
"userId": "user123",
"balance": 50000
}

> 400 Bad Request
{
"error": "잔액조회 실패"
}
---
## 상품조회 API
```
GET /api/v1/product
```
> 200 OK
{
"userId": "user123",
"productFind": 1,
"DetailInfo": "아이패드",
"qty": 5
}

> 400 Bad Request
{
"error": "상품 조회 실패"
}
---
## 주문 API
```
POST /api/v1/orders
```
> 200 OK
{
"orderId": 98765,
"userId": 12345,
"productDetailId": 67890,
"qty": 2,
"price": 15000,
"orderStatus": "ORDER_COMPLETE"
}

> 400 Bad Request
{
"error": "잔액부족"
}

> 401 Bad Request
{
"error": "재고부족"
}
---
## 결제 API
```
POST /api/v1/payment

{
  "userId": 12345,
  "orderId": 67890
}
```
> 200 OK
{
"paymentId": 98765,
"userId": 12345,
"orderId": 67890,
"price": 15000,
"qty": 2,
"status": 1,
"createAt": "2024-10-10"
}

> 400 Bad Request
{
"error": "결제 실패"
}
---
## 상위 상품 조회 API
```
GET /api/v1/product/top
```
> 200 OK
{
"productId": 98765,
"detailInfo": 12345,
"price": 15000,
"qty": 2
}

> 400 Bad Request
{
"error": "조회 실패"
}
---
## 장바구니 추가 API
```
POST
/api/v1/cart

{
  "userId": "user123",
  "productId": 67890
}
```
> 200 OK
{
"productId": 98765,
"detailInfo": 12345,
"price": 15000,
"qty": 2
}

> 400 Bad Request
{
"error": "장바구니 추가 실패"
}
---
## 장바구니 삭제 API
```
DELETE /api/v1/cart/{userId}/{productId}
```
> 200 OK
{
"success": "삭제 완료"
}

> 400 Bad Request
{
"error": "삭제 실패"
}
---
## 장바구니 조회 API
```
GET /api/v1/cart/{userId}
```
> 200 OK
{
"productId": 98765,
"detailInfo": 12345,
"price": 15000,
"qty": 2
}

> 400 Bad Request
{
"error": "장바구니 조회 실패"
}