---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614809"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="1533d-101">기본 SignedXML 및 SignedXMS 알고리즘이 SHA256으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="1533d-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="1533d-102">설명</span><span class="sxs-lookup"><span data-stu-id="1533d-102">Details</span></span>

<span data-ttu-id="1533d-103">.NET Framework 4.7 이전 버전에서는 SignedXML 및 SignedCMS의 기본값이 일부 작업에서 SHA1로 설정되었습니다. .NET Framework 4.7.1부터 SHA256은 기본적으로 이러한 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1533d-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="1533d-104">SHA1은 더 이상 안전하지 않으므로 이 변경이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1533d-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1533d-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="1533d-105">Suggestion</span></span>

<span data-ttu-id="1533d-106">다음과 같이 SHA1(안전하지 않음) 또는 SHA256이 기본적으로 사용되는지 여부를 제어하는 두 가지 새로운 컨텍스트 스위치 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1533d-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="1533d-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="1533d-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="1533d-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms .NET Framework 4.7.1 이상 버전을 대상으로 하는 애플리케이션의 경우 SHA256 사용이 바람직하지 않으면 앱 구성 파일의 [런타임](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 스위치를 추가하여 기본값을 SHA1을 기본값으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1533d-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="1533d-109">.NET Framework 4.7 이전 버전을 대상으로 하는 애플리케이션의 경우 앱 구성 파일의 [런타임](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 스위치를 추가하여 이 변경을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1533d-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="1533d-110">이름</span><span class="sxs-lookup"><span data-stu-id="1533d-110">Name</span></span>    | <span data-ttu-id="1533d-111">값</span><span class="sxs-lookup"><span data-stu-id="1533d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1533d-112">Scope</span><span class="sxs-lookup"><span data-stu-id="1533d-112">Scope</span></span>   | <span data-ttu-id="1533d-113">부</span><span class="sxs-lookup"><span data-stu-id="1533d-113">Minor</span></span>       |
| <span data-ttu-id="1533d-114">버전</span><span class="sxs-lookup"><span data-stu-id="1533d-114">Version</span></span> | <span data-ttu-id="1533d-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="1533d-115">4.7.1</span></span>       |
| <span data-ttu-id="1533d-116">형식</span><span class="sxs-lookup"><span data-stu-id="1533d-116">Type</span></span>    | <span data-ttu-id="1533d-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="1533d-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1533d-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1533d-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
