---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770837"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="1aacf-101">WCF MsmqSecureHashAlgorithm 기본값은 이제 SHA256입니다.</span><span class="sxs-lookup"><span data-stu-id="1aacf-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="1aacf-102">설명</span><span class="sxs-lookup"><span data-stu-id="1aacf-102">Details</span></span>

<span data-ttu-id="1aacf-103">.NET Framework 4.7.1부터 Msmq 메시지에 대한 WCF의 기본 메시지 서명 알고리즘은 SHA256입니다.</span><span class="sxs-lookup"><span data-stu-id="1aacf-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="1aacf-104">.NET Framework 4.7 및 이전 버전에서 기본 메시지 서명 알고리즘은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="1aacf-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1aacf-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="1aacf-105">Suggestion</span></span>

<span data-ttu-id="1aacf-106">.NET Framework 4.7.1 이상에서 이러한 변경 내용과의 호환성 문제가 발생하면 app.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 변경 내용을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aacf-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="1aacf-107">Name</span><span class="sxs-lookup"><span data-stu-id="1aacf-107">Name</span></span>    | <span data-ttu-id="1aacf-108">값</span><span class="sxs-lookup"><span data-stu-id="1aacf-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="1aacf-109">Scope</span><span class="sxs-lookup"><span data-stu-id="1aacf-109">Scope</span></span>   | <span data-ttu-id="1aacf-110">부</span><span class="sxs-lookup"><span data-stu-id="1aacf-110">Minor</span></span>   |
| <span data-ttu-id="1aacf-111">버전</span><span class="sxs-lookup"><span data-stu-id="1aacf-111">Version</span></span> | <span data-ttu-id="1aacf-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="1aacf-112">4.7.1</span></span>   |
| <span data-ttu-id="1aacf-113">형식</span><span class="sxs-lookup"><span data-stu-id="1aacf-113">Type</span></span>    | <span data-ttu-id="1aacf-114">런타임</span><span class="sxs-lookup"><span data-stu-id="1aacf-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1aacf-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1aacf-115">Affected APIs</span></span>

<span data-ttu-id="1aacf-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aacf-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
