---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496743"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="18701-101">RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="18701-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="18701-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="18701-102">Details</span></span>

<span data-ttu-id="18701-103">지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18701-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="18701-104">이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>의 지역화된 리소스를 업데이트하여 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18701-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="18701-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="18701-105">Suggestion</span></span>

<span data-ttu-id="18701-106">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="18701-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="18701-107">이름</span><span class="sxs-lookup"><span data-stu-id="18701-107">Name</span></span>    | <span data-ttu-id="18701-108">값</span><span class="sxs-lookup"><span data-stu-id="18701-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18701-109">Scope</span><span class="sxs-lookup"><span data-stu-id="18701-109">Scope</span></span>   |<span data-ttu-id="18701-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="18701-110">Edge</span></span>|
|<span data-ttu-id="18701-111">버전</span><span class="sxs-lookup"><span data-stu-id="18701-111">Version</span></span>|<span data-ttu-id="18701-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="18701-112">4.6.2</span></span>|
|<span data-ttu-id="18701-113">형식</span><span class="sxs-lookup"><span data-stu-id="18701-113">Type</span></span>|<span data-ttu-id="18701-114">런타임</span><span class="sxs-lookup"><span data-stu-id="18701-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="18701-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="18701-115">Affected APIs</span></span>

<span data-ttu-id="18701-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18701-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
