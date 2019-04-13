---
ms.openlocfilehash: 377a80e2580d035f63ee757de4687f293b120609
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761049"
---
### <a name="tls-1x-by-default-passes-the-schsendauxrecord-flag-to-the-underlying-schannel-api"></a>기본적으로 TLS 1.x는 SCH_SEND_AUX_RECORD 플래그를 기본 SCHANNEL API에 전달

|   |   |
|---|---|
|세부 정보|TLS 1.x를 사용할 때 .NET Framework는 기본 Windows SCHANNEL API에 의존합니다. .NET Framework 4.6부터는 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) 플래그가 기본적으로 SCHANNEL로 전달됩니다. 이로 인해 SCHANNEL이 데이터를 두 개의 개별 레코드(첫 번째는 단일 바이트로, 두 번째는 <em>n</em>-1바이트로)로 암호화합니다. 드문 경우지만, 데이터가 단일 레코드에 상주한다고 가정하는 클라이언트와 기존 서버 사이의 통신이 끊어지기도 합니다.|
|제안 해결 방법|이 변경으로 인해 기존 서버와의 통신이 중단된 경우 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) 플래그 전송을 비활성화하고 앱 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 있는 [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가하여 데이터를 별도의 레코드로 분리하지 않는 이전 동작으로 복원할 수 있습니다.<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] 이 설정은 이전 버전과의 호환성을 위해서만 제공됩니다. 그러나 사용하지 않는 것이 좋습니다.</blockquote> |
|범위|Microsoft Edge|
|버전|4.6|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

