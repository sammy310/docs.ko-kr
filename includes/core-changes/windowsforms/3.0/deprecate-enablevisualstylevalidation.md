---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643900"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="6c603-101">Switch.System.Windows.Forms.EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="6c603-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="6c603-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c603-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6c603-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="6c603-103">Change description</span></span>

<span data-ttu-id="6c603-104">.NET Framework에서는 애플리케이션이 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치를 통해 숫자 형태로 제공된 시각적 개체 스타일의 유효성 검사를 옵트아웃할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c603-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="6c603-105">.NET Core에서는 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c603-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6c603-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6c603-106">Version introduced</span></span>

<span data-ttu-id="6c603-107">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="6c603-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6c603-108">권장 작업</span><span class="sxs-lookup"><span data-stu-id="6c603-108">Recommended action</span></span>

<span data-ttu-id="6c603-109">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6c603-109">Remove the switch.</span></span> <span data-ttu-id="6c603-110">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c603-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="6c603-111">범주</span><span class="sxs-lookup"><span data-stu-id="6c603-111">Category</span></span>

<span data-ttu-id="6c603-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c603-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c603-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6c603-113">Affected APIs</span></span>

- <span data-ttu-id="6c603-114">없음</span><span class="sxs-lookup"><span data-stu-id="6c603-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
