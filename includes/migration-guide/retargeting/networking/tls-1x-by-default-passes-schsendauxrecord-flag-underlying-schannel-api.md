---
ms.openlocfilehash: e7f690030a5cb5605645f1ca42a6f08dcdd214f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615699"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>기본적으로 TLS 1.x는 SCH_SEND_AUX_RECORD 플래그를 기본 SCHANNEL API에 전달

#### <a name="details"></a>세부 정보

TLS 1.x를 사용할 때 .NET Framework는 기본 Windows SCHANNEL API에 의존합니다. .NET Framework 4.6부터는 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) 플래그가 기본적으로 SCHANNEL로 전달됩니다. 이렇게 하면 SCHANNEL이 암호화할 데이터를 두 개의 개별 레코드로 분할합니다. 첫 번째 레코드는 단일 바이트이고 두 번째 레코드는 <em>n</em>-1 바이트입니다. 이로 인해 간혹 데이터가 단일 레코드에 있다고 가정하고 클라이언트와 기존 서버 간의 통신이 중단되기도 합니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경으로 인해 기존 서버와의 통신이 중단된 경우 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) 플래그 전송을 비활성화하고 앱 구성 파일의 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 있는 [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가하여 데이터를 별도의 레코드로 분리하지 않는 이전 동작으로 복원할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> 이 설정은 이전 버전과의 호환성을 위해서만 제공됩니다. 그러나 사용하지 않는 것이 좋습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
