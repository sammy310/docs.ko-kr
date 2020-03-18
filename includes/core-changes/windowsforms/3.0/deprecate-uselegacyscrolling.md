---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937021"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="e28d8-101">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="e28d8-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="e28d8-102">.NET Framework 4.7.1에서 도입된 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e28d8-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e28d8-103">Change description</span></span>

<span data-ttu-id="e28d8-104">.NET Framework4.7.1부터는 개발자가 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치를 통해 독립적인 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 옵트아웃할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="e28d8-105">이 스위치는 컨텍스트 텍스트가 있는 경우 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>이 무시되고, 개발자가 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업 전에 사용해야 하는 레거시 동작을 복원했습니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="e28d8-106">자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e28d8-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="e28d8-107">.NET Core에서는 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e28d8-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e28d8-108">Version introduced</span></span>

<span data-ttu-id="e28d8-109">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="e28d8-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e28d8-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e28d8-110">Recommended action</span></span>

<span data-ttu-id="e28d8-111">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-111">Remove the switch.</span></span> <span data-ttu-id="e28d8-112">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e28d8-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e28d8-113">범주</span><span class="sxs-lookup"><span data-stu-id="e28d8-113">Category</span></span>

<span data-ttu-id="e28d8-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e28d8-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e28d8-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e28d8-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
