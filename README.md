# 광고 링크 변환 안내

                     |
| `{click_id}`       | string | yes      | 클릭 아이디 (유니크 값 / ex: 사용자 고유 값_timestamp 값) |
| `{advertising_id}` | string | yes      | 사용자 구글 광고 아이디 (ADID)                            |

변환 예제:

```
http://app.appsflyer.com/com.tmon?af_siteid=100000&af_c_id=1&pid=platform9_int&c=test&af_click_lookback=1d&clickid=1_20200101000001&advertising_id=2d6f570e-abc5-4acf-ab53-d268cabff766&idfa=&is_retargeting=true&af_ios_url=http%3A%2F%2Fgo.tmon.co.kr%2F%3Fv%3D0%26ln%3D829362%26jp%3D90062&af_android_url=http%3A%2F%2Fgo.tmon.co.kr%2F%3Fv%3D0%26ln%3D829362%26jp%3D90062
```


# Tmon Report API

> Version 0.1: 2020-03-02
>
> 

요청 URL:

```
GET https://api.oneplatform.kr/api/report/tmon
```

파라미터:

| Attribute    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| `start_date` | string | yes      | 검색 시작일 |
| `end_date`   | string | yes      | 검색 종료일 |
| `af_sub1`    | string | optional | af_sub1     |
| `af_sub2`    | string | optional | af_sub2     |
| `af_sub3`    | string | optional | af_sub3     |
| `af_sub4`    | string | optional | af_sub4     |
| `af_sub5`    | string | optional | af_sub5     |

요청 예제:

```
curl --header "Authorization: Bearer <your_access_token>" --header "Accept: aplication/json" https://api.oneplatform.kr/api/report/tmon
```

```json
{
    "start_date": "2020-02-20",
    "end_date": "2020-03-02"
}
```

응답 예제:

| http Status Code | description   |
| ---------------- | ------------- |
| 200              | 성공          |
| 401              | 인증 실패     |
| 422              | 파라미터 오류 |

```json
{
    "items": {
        "2020-02-20": [
            {
                "date": "2020-02-20",
                "campaign": 1,
                "count": 4,
                "amount": 26600
            },
            {
                "date": "2020-02-20",
                "campaign": 2,
                "count": 15,
                "amount": 157200
            }
        ],
        "2020-02-21": [
            {
                "date": "2020-02-21",
                "campaign": 1,
                "count": 1,
                "amount": 9800
            },
            {
                "date": "2020-02-21",
                "campaign": 2,
                "count": 5,
                "amount": 54100
            }
        ]
    }
}
```

