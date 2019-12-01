---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643894"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="fd359-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="fd359-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="fd359-102">.NET Framework 4.6.1에서 도입된 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd359-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fd359-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="fd359-103">Change description</span></span>

<span data-ttu-id="fd359-104">.NET Framework 4.6.1부터는 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현으로 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메시지를 호출할 때 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 호환성 스위치가 가능한 <xref:System.IndexOutOfRangeException> 예외를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="fd359-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="fd359-105">자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd359-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="fd359-106">.NET Core에서는 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd359-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fd359-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fd359-107">Version introduced</span></span>

<span data-ttu-id="fd359-108">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="fd359-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fd359-109">권장 작업</span><span class="sxs-lookup"><span data-stu-id="fd359-109">Recommended action</span></span>

<span data-ttu-id="fd359-110">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fd359-110">Remove the switch.</span></span> <span data-ttu-id="fd359-111">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd359-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="fd359-112">범주</span><span class="sxs-lookup"><span data-stu-id="fd359-112">Category</span></span>

<span data-ttu-id="fd359-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd359-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fd359-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fd359-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
