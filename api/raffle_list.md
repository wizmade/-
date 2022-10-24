# Beta 단계인 API

{% hint style="danger" %}
**※ 주의 ※**

API는 현재 Beta 기능입니다

API의 사양은 향후 변경되거나 삭제될 수 있습니다.

만약 삭제/변경을 원치 않으실 경우 고객센터로 문의주시길 바랍니다.
{% endhint %}



{% swagger method="get" path="" baseUrl="https://onlineraffle.co.kr/Api/Event/Raffle_List" summary="응모내역 보기 API" %}
{% swagger-description %}
로그인한 회원이 자신의 응모내역을 반환하는 API 입니다.

\


요청한 결과를 html 형식으로 반환합니다.
{% endswagger-description %}

{% swagger-parameter in="query" name="mall_id" required="true" %}
쇼핑몰의 기본 아이디입니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="member_id" required="true" %}
응모내역을 조회 할 회원의 아이디입니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="style" %}
반환될 디자인을 입력합니다.

\+ 입력값 : 'pc', 'mobile'

\+ 기본값 : 'pc'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="last_id" %}
페이징 처리용 변수입니다

마지막으로 반환받은 em\_no(응모번호)를 입력하면 해당 번호로 부터 50개의 응모내역을 불러옵니다
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="HTMI 형식으로 반환 (응모내역이 없을 떄)" %}
<pre class="language-html"><code class="lang-html"><strong>...CSS 코드 반환 위치 ...  
</strong>&#x3C;thead>
    &#x3C;tr>
      &#x3C;th class="bl0">응모번호&#x3C;/th>
      &#x3C;th>응모상품&#x3C;/th>
      &#x3C;th>응모일시&#x3C;/th>
      &#x3C;th class="br0">당첨여부&#x3C;/th>
    &#x3C;/tr>
  &#x3C;/thead>
  &#x3C;tbody>
    &#x3C;tr>&#x3C;td colspan='4' align='center'>응모내역이 없습니다.&#x3C;/td>&#x3C;/tr>  &#x3C;/tbody>
&#x3C;/table></code></pre>
{% endswagger-response %}

{% swagger-response status="200: OK" description="HTMI 형식으로 반환 (응모내역이 있을 떄)" %}
```html
...CSS 코드 반환 위치 ...  
<thead>
    <tr>
      <th class="bl0">응모번호</th>
      <th>응모상품</th>
      <th>응모일시</th>
      <th class="br0">당첨여부</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td class="em_no">0000138816</td>
        <td class="em_name">
          <a href='https://wizmade0607.cafe24.com/product/detail.html?product_no=12'><strong>재고관리/옵션없음</strong></a><div><ul><li style='list-style: disc;'>5 개</li></ul></div>        </td>
        <td class="em_date">
          <span class='ymd'>2021-12-24</span><span class='hmi mobile_hidden'>16:16:41</span>        </td>
        <td class="em_statue">
          <button type='button' class='btn btn_color_type2'>미당첨</button>        </td>
      </tr>
    </tbody>
</table>
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://onlineraffle.co.kr/Api/Event/Raffle_Count" summary="이벤트 응모자수 반환 API" %}
{% swagger-description %}
특정 이벤트에 응모자가 몇명인지를 표시합니다.

\


요청한 결과를 html 형식으로 반환합니다.
{% endswagger-description %}

{% swagger-parameter in="query" name="mall_id" required="true" %}
쇼핑몰의 기본 아이디입니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="쇼핑몰의 기본 아이디입니다." %}
특정 이벤트에 대한 응모자수만 표시하고 싶을 때 사용합니다.

이벤트의 고유번호를 입력해주시면 되며, 이벤트 고유번호는 래플 관리자 페이지 > 이벤트 수정에서 확인하실 수 있습니다.

입력하지 않으실 경우 모든 이벤트에 대한 누적 응모자수가 표시됩니다.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="style" %}
반환될 디자인을 입력합니다.

\+ 입력값 : 'default', 'blank'

\+ 기본값 : 'blank'
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="HTMI 형식으로 반환" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
