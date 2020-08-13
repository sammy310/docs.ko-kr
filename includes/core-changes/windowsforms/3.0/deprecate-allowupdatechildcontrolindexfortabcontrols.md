---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556210"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="656e0-101">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="656e0-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="656e0-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치는 .NET Framework 4.6 이상 버전의 Windows Forms에서 지원되지만, .NET Core 또는 .NET 5.0 이상에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="656e0-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="656e0-103">Change description</span></span>

<span data-ttu-id="656e0-104">.NET Framework 4.6 이상 버전에서 탭을 선택하면 해당 컨트롤 컬렉션이 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="656e0-105">이 동작을 사용하지 않으려는 경우, `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치를 통해 애플리케이션에서 다시 정렬을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="656e0-106">.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="656e0-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="656e0-107">Version introduced</span></span>

<span data-ttu-id="656e0-108">3.0</span><span class="sxs-lookup"><span data-stu-id="656e0-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="656e0-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="656e0-109">Recommended action</span></span>

<span data-ttu-id="656e0-110">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-110">Remove the switch.</span></span> <span data-ttu-id="656e0-111">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="656e0-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="656e0-112">범주</span><span class="sxs-lookup"><span data-stu-id="656e0-112">Category</span></span>

<span data-ttu-id="656e0-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="656e0-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="656e0-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="656e0-114">Affected APIs</span></span>

- <span data-ttu-id="656e0-115">None</span><span class="sxs-lookup"><span data-stu-id="656e0-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
