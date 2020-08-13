---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556208"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="5622c-101">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="5622c-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="5622c-102">.NET Framework 4.8에서 도입된 `Switch.System.Windows.Forms.UseLegacyImages` 호환성 스위치는 .NET Core 또는 .NET 5.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5622c-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="5622c-103">Change description</span></span>

<span data-ttu-id="5622c-104">.NET Framework 4.8부터는 `Switch.System.Windows.Forms.UseLegacyImages` 호환성 스위치가 높은 DPI 환경의 ClickOnce 시나리오에서 가능한 이미지 크기 조정 문제를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-104">Starting with .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="5622c-105">`true`로 설정하면, 사용자가 이 스위치를 통해 배율이 100%보다 큰 값으로 설정된 높은 DPI 디스플레이에서 레거시 이미지 크기 조정을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="5622c-106">자세한 내용은 GitHub에서 [.NET Framework 4.8 릴리스 정보](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5622c-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="5622c-107">.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.UseLegacyImages` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5622c-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="5622c-108">Version introduced</span></span>

<span data-ttu-id="5622c-109">3.0</span><span class="sxs-lookup"><span data-stu-id="5622c-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5622c-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="5622c-110">Recommended action</span></span>

<span data-ttu-id="5622c-111">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-111">Remove the switch.</span></span> <span data-ttu-id="5622c-112">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5622c-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="5622c-113">범주</span><span class="sxs-lookup"><span data-stu-id="5622c-113">Category</span></span>

<span data-ttu-id="5622c-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5622c-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5622c-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5622c-115">Affected APIs</span></span>

- <span data-ttu-id="5622c-116">None</span><span class="sxs-lookup"><span data-stu-id="5622c-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
