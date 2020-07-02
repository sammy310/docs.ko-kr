---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622372"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="452dc-101">RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="452dc-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="452dc-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="452dc-102">Details</span></span>

<span data-ttu-id="452dc-103">지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452dc-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="452dc-104">이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>의 지역화된 리소스를 업데이트하여 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452dc-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="452dc-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="452dc-105">Suggestion</span></span>

<span data-ttu-id="452dc-106">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="452dc-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="452dc-107">이름</span><span class="sxs-lookup"><span data-stu-id="452dc-107">Name</span></span>    | <span data-ttu-id="452dc-108">값</span><span class="sxs-lookup"><span data-stu-id="452dc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="452dc-109">Scope</span><span class="sxs-lookup"><span data-stu-id="452dc-109">Scope</span></span>   |<span data-ttu-id="452dc-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="452dc-110">Edge</span></span>|
|<span data-ttu-id="452dc-111">버전</span><span class="sxs-lookup"><span data-stu-id="452dc-111">Version</span></span>|<span data-ttu-id="452dc-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="452dc-112">4.6.2</span></span>|
|<span data-ttu-id="452dc-113">형식</span><span class="sxs-lookup"><span data-stu-id="452dc-113">Type</span></span>|<span data-ttu-id="452dc-114">런타임</span><span class="sxs-lookup"><span data-stu-id="452dc-114">Runtime</span></span>|
