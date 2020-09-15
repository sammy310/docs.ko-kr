---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614647"
---
### <a name="throttle-concurrent-requests-per-session"></a>세션당 동시 요청 수 조절

#### <a name="details"></a>설명

.NET Framework 4.6.2 이전 버전에서 ASP.NET은 같은 Sessionid를 사용하여 요청을 순차적으로 실행하고, ASP.NET은 항상 기본적으로 쿠키를 통해 Sessionid를 발급합니다. 페이지가 응답하는 데 시간이 오래 걸릴 때 브라우저에서 <kbd>F5</kbd> 키를 누르면 서버 성능이 크게 저하됩니다. 수정 사항에서는 카운터를 추가하여 큐에 대기 중인 요청을 추적하고 지정된 한도를 초과할 때 요청을 종료합니다. 기본값은 50입니다. 이 한도에 도달하면 이벤트 로그에 경고가 기록되고 HTTP 500 응답이 IIS 로그에 기록될 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

이전 동작을 복원하려면 web.config 파일에 다음 설정을 추가하여 새 동작을 옵트아웃(opt out)할 수 있습니다.

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7         |
| 형식    | 대상 변경 |
