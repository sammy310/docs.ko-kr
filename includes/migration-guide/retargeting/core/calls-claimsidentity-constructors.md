---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614638"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="913f1-101">ClaimsIdentity 생성자 호출</span><span class="sxs-lookup"><span data-stu-id="913f1-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="913f1-102">설명</span><span class="sxs-lookup"><span data-stu-id="913f1-102">Details</span></span>

<span data-ttu-id="913f1-103">.NET Framework 4.6.2부터는 <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 매개 변수로 <xref:System.Security.Claims.ClaimsIdentity> 생성자가 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성을 설정하는 방법이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="913f1-104"><xref:System.Security.Principal.IIdentity?displayProperty=fullName> 인수가 <xref:System.Security.Claims.ClaimsIdentity> 개체이고 해당 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 `null`이 아닌 경우 <xref:System.Security.Claims.ClaimsIdentity.Clone> 메서드를 사용하여 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="913f1-105">Framework 4.6.1 이전 버전에서 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성은 기존 참조로 첨부됩니다. 이 변경으로 인해 .NET Framework 4.6.2부터는 새 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 생성자의 <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 인수의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="913f1-106">.NET Framework 4.6.1 이전 버전에서는 이 속성이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="913f1-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="913f1-107">Suggestion</span></span>

<span data-ttu-id="913f1-108">이 동작을 원치 않을 경우 애플리케이션 구성 파일에서 `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` 스위치를 `true`로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="913f1-109">이렇게 하려면 web.config 파일의 `<runtime>` 섹션에 다음을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f1-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="913f1-110">이름</span><span class="sxs-lookup"><span data-stu-id="913f1-110">Name</span></span>    | <span data-ttu-id="913f1-111">값</span><span class="sxs-lookup"><span data-stu-id="913f1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="913f1-112">Scope</span><span class="sxs-lookup"><span data-stu-id="913f1-112">Scope</span></span>   | <span data-ttu-id="913f1-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="913f1-113">Edge</span></span>        |
| <span data-ttu-id="913f1-114">버전</span><span class="sxs-lookup"><span data-stu-id="913f1-114">Version</span></span> | <span data-ttu-id="913f1-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="913f1-115">4.6.2</span></span>       |
| <span data-ttu-id="913f1-116">형식</span><span class="sxs-lookup"><span data-stu-id="913f1-116">Type</span></span>    | <span data-ttu-id="913f1-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="913f1-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="913f1-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="913f1-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
