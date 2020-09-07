---
ms.openlocfilehash: 4e685722271a8079e727ea9c2e0e501f68b30fc9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497664"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="e62d5-101">기본 앱 도메인에 대한 TargetFrameworkName을 설정하지 않으면 더 이상 null을 기본값으로 하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="e62d5-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="e62d5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e62d5-102">Details</span></span>

<span data-ttu-id="e62d5-103">이전에는 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>이 명시적으로 설정되지 않은 경우 기본 앱 도메인에서 null이었습니다.</span><span class="sxs-lookup"><span data-stu-id="e62d5-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="e62d5-104">4\.6부터 기본 응용 프로그램 도메인에 대한 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> 속성은 TargetFrameworkAttribute에서 파생된 기본값을 가집니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="e62d5-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="e62d5-105">기본이 아닌 앱 도메인은 명시적으로 재정의되지 않으면 해당 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>을 기본 응용 프로그램 도메인(4.6에서 기본값을 null로 하지 않는)에서 계속 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="e62d5-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e62d5-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e62d5-106">Suggestion</span></span>

<span data-ttu-id="e62d5-107">코드는 기본값을 null로 하는 <xref:System.AppDomainSetup.TargetFrameworkName>에 종속하지 않도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62d5-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="e62d5-108">이 속성이 계속 null을 평가해야 하는 경우 명시적으로 해당 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e62d5-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="e62d5-109">Name</span><span class="sxs-lookup"><span data-stu-id="e62d5-109">Name</span></span>    | <span data-ttu-id="e62d5-110">값</span><span class="sxs-lookup"><span data-stu-id="e62d5-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e62d5-111">Scope</span><span class="sxs-lookup"><span data-stu-id="e62d5-111">Scope</span></span>   |<span data-ttu-id="e62d5-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e62d5-112">Edge</span></span>|
|<span data-ttu-id="e62d5-113">버전</span><span class="sxs-lookup"><span data-stu-id="e62d5-113">Version</span></span>|<span data-ttu-id="e62d5-114">4.6</span><span class="sxs-lookup"><span data-stu-id="e62d5-114">4.6</span></span>|
|<span data-ttu-id="e62d5-115">형식</span><span class="sxs-lookup"><span data-stu-id="e62d5-115">Type</span></span>|<span data-ttu-id="e62d5-116">런타임</span><span class="sxs-lookup"><span data-stu-id="e62d5-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e62d5-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e62d5-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.TargetFrameworkName`

-->
