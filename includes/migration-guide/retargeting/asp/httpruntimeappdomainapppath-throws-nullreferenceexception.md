---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617541"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="7d054-101">HttpRuntime.AppDomainAppPath가 NullReferenceException을 Throw함</span><span class="sxs-lookup"><span data-stu-id="7d054-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="7d054-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7d054-102">Details</span></span>

<span data-ttu-id="7d054-103">.NET Framework 4.6.2에서 런타임은 null 문자를 포함하는 `P:System.Web.HttpRuntime.AppDomainAppPath` 값을 검색할 때 `T:System.NullReferenceException`를 throw합니다. .NET Framework 4.6.1 이전 버전에서 런타임은 `T:System.ArgumentNullException`를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7d054-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d054-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="7d054-104">Suggestion</span></span>

<span data-ttu-id="7d054-105">이러한 변경에 대처하기 위해 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d054-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="7d054-106">애플리케이션이 .NET Framework 4.6.2에서 실행 중인 경우 `T:System.NullReferenceException`를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d054-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="7d054-107">.NET Framework 4.7로 업그레이드하면 이전 동작이 복원되고 `T:System.ArgumentNullException`가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d054-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="7d054-108">이름</span><span class="sxs-lookup"><span data-stu-id="7d054-108">Name</span></span>    | <span data-ttu-id="7d054-109">값</span><span class="sxs-lookup"><span data-stu-id="7d054-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d054-110">Scope</span><span class="sxs-lookup"><span data-stu-id="7d054-110">Scope</span></span>   | <span data-ttu-id="7d054-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7d054-111">Edge</span></span>        |
| <span data-ttu-id="7d054-112">버전</span><span class="sxs-lookup"><span data-stu-id="7d054-112">Version</span></span> | <span data-ttu-id="7d054-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7d054-113">4.6.2</span></span>       |
| <span data-ttu-id="7d054-114">형식</span><span class="sxs-lookup"><span data-stu-id="7d054-114">Type</span></span>    | <span data-ttu-id="7d054-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="7d054-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7d054-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7d054-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
