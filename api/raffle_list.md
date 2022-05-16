# 응모내역

## 소개

로그인한 회원이 자신의 응모내역을 반환하는 API 입니다.\
요청한 결과를 html 형식으로 반환합니다.

```
※ 주의 ※
API는 현재 Beta 기능입니다 
API의 사양은 향후 변경되거나 삭제될 수 있습니다.
만약 삭제/변경을 원치 않으실 경우 고객센터로 문의주시길 바랍니다.
```

## Request

### URL

```http
GET /Api/Event/Raffle_List HTTP/1.1
Host: onlineraffle.co.kr
```

### Parameter

| Name       | Description                                                            | Required |
| ---------- | ---------------------------------------------------------------------- | -------- |
| mall\_id   | 쇼핑몰의 기본 아이디입니다.                                                        | O        |
| member\_id | 응모내역을 조회 할 회원의 아이디입니다.                                                 | O        |
| style      | <p>반환될 디자인을 입력합니다.</p><p>+ 입력값 : 'pc', 'mobile'</p><p>+ 기본값 : 'pc'</p> | X        |

## Response

html 형식으로 반환됩니다.



