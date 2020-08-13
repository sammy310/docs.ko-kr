---
ms.openlocfilehash: ee4a27dde9f1e7756401e3d8b709514082f5d3b1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556212"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="50880-101">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="50880-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="50880-102">.NET Framework 4.7.1에서 도입된 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치는 .NET Core 또는 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50880-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="50880-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="50880-103">Change description</span></span>

<span data-ttu-id="50880-104">.NET Framework 4.7.1부터는 개발자가 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치를 통해 독립적인 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 옵트아웃할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="50880-104">Starting with .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="50880-105">이 스위치는 컨텍스트 텍스트가 있는 경우 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>이 무시되고, 개발자가 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업 전에 사용해야 하는 레거시 동작을 복원했습니다.</span><span class="sxs-lookup"><span data-stu-id="50880-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="50880-106">자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50880-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="50880-107">.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50880-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="50880-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="50880-108">Version introduced</span></span>

<span data-ttu-id="50880-109">3.0</span><span class="sxs-lookup"><span data-stu-id="50880-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="50880-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="50880-110">Recommended action</span></span>

<span data-ttu-id="50880-111">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="50880-111">Remove the switch.</span></span> <span data-ttu-id="50880-112">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50880-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="50880-113">범주</span><span class="sxs-lookup"><span data-stu-id="50880-113">Category</span></span>

<span data-ttu-id="50880-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50880-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="50880-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="50880-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
