---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760638"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="dafeb-101">RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dafeb-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dafeb-102">설명</span><span class="sxs-lookup"><span data-stu-id="dafeb-102">Details</span></span>|<span data-ttu-id="dafeb-103">지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dafeb-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="dafeb-104">이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>의 지역화된 리소스를 업데이트하여 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dafeb-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="dafeb-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="dafeb-105">Suggestion</span></span>|<span data-ttu-id="dafeb-106">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="dafeb-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="dafeb-107">범위</span><span class="sxs-lookup"><span data-stu-id="dafeb-107">Scope</span></span>|<span data-ttu-id="dafeb-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dafeb-108">Edge</span></span>|
|<span data-ttu-id="dafeb-109">버전</span><span class="sxs-lookup"><span data-stu-id="dafeb-109">Version</span></span>|<span data-ttu-id="dafeb-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="dafeb-110">4.6.2</span></span>|
|<span data-ttu-id="dafeb-111">형식</span><span class="sxs-lookup"><span data-stu-id="dafeb-111">Type</span></span>|<span data-ttu-id="dafeb-112">런타임</span><span class="sxs-lookup"><span data-stu-id="dafeb-112">Runtime</span></span>|

