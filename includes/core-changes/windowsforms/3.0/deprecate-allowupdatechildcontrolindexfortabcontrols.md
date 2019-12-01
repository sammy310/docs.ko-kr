---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643888"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="eeeec-101">Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="eeeec-101">Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="eeeec-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치는 .NET Framework 4.6 이상 버전의 Windows Forms에서 지원되지만, .NET Core 3.0부터 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eeeec-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="eeeec-103">Change description</span></span>

<span data-ttu-id="eeeec-104">.NET Framework 4.6 이상 버전에서 탭을 선택하면 해당 컨트롤 컬렉션이 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="eeeec-105">이 동작을 사용하지 않으려는 경우, `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치를 통해 애플리케이션에서 다시 정렬을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="eeeec-106">.NET Core에서는 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eeeec-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="eeeec-107">Version introduced</span></span>

<span data-ttu-id="eeeec-108">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="eeeec-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eeeec-109">권장 작업</span><span class="sxs-lookup"><span data-stu-id="eeeec-109">Recommended action</span></span>

<span data-ttu-id="eeeec-110">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-110">Remove the switch.</span></span> <span data-ttu-id="eeeec-111">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeeec-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="eeeec-112">범주</span><span class="sxs-lookup"><span data-stu-id="eeeec-112">Category</span></span>

<span data-ttu-id="eeeec-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eeeec-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eeeec-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="eeeec-114">Affected APIs</span></span>

- <span data-ttu-id="eeeec-115">없음</span><span class="sxs-lookup"><span data-stu-id="eeeec-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
