---
ms.openlocfilehash: 207dba9327cfd6debd15c5573697f8950b6c2c95
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218097"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="269d6-101">기본적으로 TLS 1.x는 SCH_SEND_AUX_RECORD 플래그를 기본 SCHANNEL API에 전달</span><span class="sxs-lookup"><span data-stu-id="269d6-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="269d6-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="269d6-102">Details</span></span>

<span data-ttu-id="269d6-103">TLS 1.x를 사용할 때 .NET Framework는 기본 Windows SCHANNEL API에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="269d6-104">.NET Framework 4.6부터는 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) 플래그가 기본적으로 SCHANNEL로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="269d6-105">이렇게 하면 SCHANNEL이 암호화할 데이터를 두 개의 개별 레코드로 분할합니다. 첫 번째 레코드는 단일 바이트이고 두 번째 레코드는 <em>n</em>-1 바이트입니다. 이로 인해 간혹 데이터가 단일 레코드에 있다고 가정하고 클라이언트와 기존 서버 간의 통신이 중단되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="269d6-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="269d6-106">Suggestion</span></span>

<span data-ttu-id="269d6-107">이 변경으로 인해 기존 서버와의 통신이 중단된 경우 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) 플래그 전송을 비활성화하고 앱 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 있는 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가하여 데이터를 별도의 레코드로 분리하지 않는 이전 동작으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="269d6-108">이 설정은 이전 버전과의 호환성을 위해서만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="269d6-109">그러나 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="269d6-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="269d6-110">이름</span><span class="sxs-lookup"><span data-stu-id="269d6-110">Name</span></span>    | <span data-ttu-id="269d6-111">값</span><span class="sxs-lookup"><span data-stu-id="269d6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="269d6-112">Scope</span><span class="sxs-lookup"><span data-stu-id="269d6-112">Scope</span></span>   | <span data-ttu-id="269d6-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="269d6-113">Edge</span></span>        |
| <span data-ttu-id="269d6-114">버전</span><span class="sxs-lookup"><span data-stu-id="269d6-114">Version</span></span> | <span data-ttu-id="269d6-115">4.6</span><span class="sxs-lookup"><span data-stu-id="269d6-115">4.6</span></span>         |
| <span data-ttu-id="269d6-116">형식</span><span class="sxs-lookup"><span data-stu-id="269d6-116">Type</span></span>    | <span data-ttu-id="269d6-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="269d6-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="269d6-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="269d6-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
