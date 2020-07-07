---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615682"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="520d0-101">인증서 EKU OID 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="520d0-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="520d0-102">설명</span><span class="sxs-lookup"><span data-stu-id="520d0-102">Details</span></span>

<span data-ttu-id="520d0-103">.NET Framework 4.6부터는 <xref:System.Net.Security.SslStream> 또는 <xref:System.Net.ServicePointManager> 클래스가 EKU(향상된 키 사용) OID(개체 식별자) 유효성 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="520d0-104">EKU(향상된 키 사용) 확장은 키를 사용하는 애플리케이션을 나타내는 OID(개체 식별자)의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="520d0-105">EKU OID 유효성 검사는 원격 인증서 콜백을 사용하여 원격 인증서가 원하는 용도에 맞는 올바른 OID를 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="520d0-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="520d0-106">Suggestion</span></span>

<span data-ttu-id="520d0-107">이 변경이 바람직하지 않은 경우 다음 스위치를 앱 구성 파일의 [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)에 있는 [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)에 추가하여 인증서 EKU OID 유효성 검사를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="520d0-108">이 설정은 이전 버전과의 호환성을 위해서만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="520d0-109">그러나 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="520d0-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="520d0-110">이름</span><span class="sxs-lookup"><span data-stu-id="520d0-110">Name</span></span>    | <span data-ttu-id="520d0-111">값</span><span class="sxs-lookup"><span data-stu-id="520d0-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="520d0-112">Scope</span><span class="sxs-lookup"><span data-stu-id="520d0-112">Scope</span></span>   | <span data-ttu-id="520d0-113">부</span><span class="sxs-lookup"><span data-stu-id="520d0-113">Minor</span></span>       |
| <span data-ttu-id="520d0-114">버전</span><span class="sxs-lookup"><span data-stu-id="520d0-114">Version</span></span> | <span data-ttu-id="520d0-115">4.6</span><span class="sxs-lookup"><span data-stu-id="520d0-115">4.6</span></span>         |
| <span data-ttu-id="520d0-116">형식</span><span class="sxs-lookup"><span data-stu-id="520d0-116">Type</span></span>    | <span data-ttu-id="520d0-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="520d0-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="520d0-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="520d0-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
