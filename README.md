# Tmon Report API

> Version 0.1: 2020-03-02
>
> 

요청 URL:

```
GET https://oneplatform.kr/api/report/tmon
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
curl --header "Authorization: Bearer <your_access_token>" --header "Accept: aplication/json" https://oneplatform.kr/api/report/tmon
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

