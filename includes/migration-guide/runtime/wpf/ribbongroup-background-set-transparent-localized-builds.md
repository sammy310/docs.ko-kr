---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802565"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="97ec5-101">RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ec5-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="97ec5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="97ec5-102">Details</span></span>|<span data-ttu-id="97ec5-103">지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97ec5-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="97ec5-104">이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>의 지역화된 리소스를 업데이트하여 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97ec5-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="97ec5-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="97ec5-105">Suggestion</span></span>|<span data-ttu-id="97ec5-106">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="97ec5-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="97ec5-107">범위</span><span class="sxs-lookup"><span data-stu-id="97ec5-107">Scope</span></span>|<span data-ttu-id="97ec5-108">가장자리</span><span class="sxs-lookup"><span data-stu-id="97ec5-108">Edge</span></span>|
|<span data-ttu-id="97ec5-109">Version</span><span class="sxs-lookup"><span data-stu-id="97ec5-109">Version</span></span>|<span data-ttu-id="97ec5-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="97ec5-110">4.6.2</span></span>|
|<span data-ttu-id="97ec5-111">형식</span><span class="sxs-lookup"><span data-stu-id="97ec5-111">Type</span></span>|<span data-ttu-id="97ec5-112">런타임</span><span class="sxs-lookup"><span data-stu-id="97ec5-112">Runtime</span></span>|
