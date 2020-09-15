---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614820"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="c3157-101">MemberDescriptor.Equals의 잘못된 구현</span><span class="sxs-lookup"><span data-stu-id="c3157-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="c3157-102">설명</span><span class="sxs-lookup"><span data-stu-id="c3157-102">Details</span></span>

<span data-ttu-id="c3157-103"><xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 메서드의 원래 구현은 비교되는 개체의 두 가지 문자열 속성을 비교합니다. 즉, 범주 이름과 설명 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="c3157-104">수정은 첫 번째 개체의 <xref:System.ComponentModel.MemberDescriptor.Category>를 두 번째의 <xref:System.ComponentModel.MemberDescriptor.Category>와 비교하고, 첫 번째의 <xref:System.ComponentModel.MemberDescriptor.Description>을 두 번째의 <xref:System.ComponentModel.MemberDescriptor.Description>과 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c3157-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c3157-105">Suggestion</span></span>

<span data-ttu-id="c3157-106">애플리케이션이 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>에 종속되어 있고 설명자가 동일할 때 `false`를 반환하는 경우 및 .NET Framework 4.6.2 이상 버전을 대상으로 하는 경우에 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="c3157-107"><xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 메서드를 호출하는 것 외에도 <xref:System.ComponentModel.MemberDescriptor.Category> 및 <xref:System.ComponentModel.MemberDescriptor.Description> 필드를 수동으로 비교하도록 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="c3157-108">app.config 파일에 다음 값을 추가하여 이러한 변경 내용을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="c3157-109">애플리케이션이 .NET Framework 4.6.1 이하를 대상으로 하고 .NET Framework 4.6.2 이상에서 실행되는 경우 이 변경 내용을 활성화하려면 app.config 파일에 다음 값을 추가하여 호환성 스위치를 `false`로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3157-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="c3157-110">이름</span><span class="sxs-lookup"><span data-stu-id="c3157-110">Name</span></span>    | <span data-ttu-id="c3157-111">값</span><span class="sxs-lookup"><span data-stu-id="c3157-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c3157-112">Scope</span><span class="sxs-lookup"><span data-stu-id="c3157-112">Scope</span></span>   | <span data-ttu-id="c3157-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c3157-113">Edge</span></span>        |
| <span data-ttu-id="c3157-114">버전</span><span class="sxs-lookup"><span data-stu-id="c3157-114">Version</span></span> | <span data-ttu-id="c3157-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c3157-115">4.6.2</span></span>       |
| <span data-ttu-id="c3157-116">형식</span><span class="sxs-lookup"><span data-stu-id="c3157-116">Type</span></span>    | <span data-ttu-id="c3157-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c3157-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c3157-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c3157-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
