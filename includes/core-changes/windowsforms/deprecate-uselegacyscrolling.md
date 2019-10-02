---
ms.openlocfilehash: 459e7e1f0b5543f069682dadf60668e94b472377
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181724"
---
### <a name="switchsystemwindowsformsdomainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="d1970-101">Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="d1970-101">Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="d1970-102">.NET Framework 4.7.1에서 도입된 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d1970-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d1970-103">Change description</span></span>

<span data-ttu-id="d1970-104">.NET Framework4.7.1부터는 개발자가 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치를 통해 독립적인 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 옵트아웃할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="d1970-105">이 스위치는 컨텍스트 텍스트가 있는 경우 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>이 무시되고, 개발자가 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업 전에 사용해야 하는 레거시 동작을 복원했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="d1970-106">자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1970-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="d1970-107">.NET Core에서는 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d1970-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1970-108">Version introduced</span></span>

<span data-ttu-id="d1970-109">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="d1970-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d1970-110">권장 작업</span><span class="sxs-lookup"><span data-stu-id="d1970-110">Recommended action</span></span>

<span data-ttu-id="d1970-111">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-111">Remove the switch.</span></span> <span data-ttu-id="d1970-112">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1970-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d1970-113">범주</span><span class="sxs-lookup"><span data-stu-id="d1970-113">Category</span></span>

<span data-ttu-id="d1970-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1970-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d1970-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d1970-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
