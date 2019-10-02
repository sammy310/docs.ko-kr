---
ms.openlocfilehash: bb163d5a6eb3d926a44a83ea79572c3a497bbe8d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181736"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="570cd-101">Microsoft.VisualBasic.Devices 네임스페이스의 형식을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="570cd-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="570cd-102"><xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="570cd-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="570cd-103">Version introduced</span></span>

<span data-ttu-id="570cd-104">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="570cd-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="570cd-105">세부 정보</span><span class="sxs-lookup"><span data-stu-id="570cd-105">Details</span></span>

<span data-ttu-id="570cd-106">일부 .NET Core 3.0 미리 보기 릴리스에서는 <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="570cd-107">.NET Core 3.0 미리 보기 9부터는 해당 형식을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="570cd-108">후속 릴리스에서 불필요한 어셈블리 종속성이나 호환성이 손상되는 변경을 방지하기 위해 형식을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="570cd-109">권장 작업</span><span class="sxs-lookup"><span data-stu-id="570cd-109">Recommended action</span></span>

<span data-ttu-id="570cd-110">코드에서 <xref:Microsoft.VisualBasic.Devices> 형식과 해당 멤버를 사용해야 하는 경우, .NET 클래스 라이브러리의 해당 형식이나 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="570cd-111">예를 들어 <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> 클래스와 동등한 기능은 <xref:System.DateTime?displayProperty=nameWithType> 및 <xref:System.Environment?displayProperty=nameWithType> 형식에서 제공되고, <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> 클래스와 동등한 기능은 <xref:System.IO.Ports?displayProperty=nameWithType> 네임스페이스의 형식에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="570cd-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="570cd-112">범주</span><span class="sxs-lookup"><span data-stu-id="570cd-112">Category</span></span>

<span data-ttu-id="570cd-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="570cd-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="570cd-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="570cd-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

