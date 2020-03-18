---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937055"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="3ae99-101">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="3ae99-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="3ae99-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치는 .NET Framework 4.6 이상 버전의 Windows Forms에서 지원되지만, .NET Core 3.0부터 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3ae99-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3ae99-103">Change description</span></span>

<span data-ttu-id="3ae99-104">.NET Framework 4.6 이상 버전에서 탭을 선택하면 해당 컨트롤 컬렉션이 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="3ae99-105">이 동작을 사용하지 않으려는 경우, `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 호환성 스위치를 통해 애플리케이션에서 다시 정렬을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="3ae99-106">.NET Core에서는 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ae99-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3ae99-107">Version introduced</span></span>

<span data-ttu-id="3ae99-108">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="3ae99-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ae99-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3ae99-109">Recommended action</span></span>

<span data-ttu-id="3ae99-110">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-110">Remove the switch.</span></span> <span data-ttu-id="3ae99-111">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ae99-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="3ae99-112">범주</span><span class="sxs-lookup"><span data-stu-id="3ae99-112">Category</span></span>

<span data-ttu-id="3ae99-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ae99-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ae99-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3ae99-114">Affected APIs</span></span>

- <span data-ttu-id="3ae99-115">None</span><span class="sxs-lookup"><span data-stu-id="3ae99-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
