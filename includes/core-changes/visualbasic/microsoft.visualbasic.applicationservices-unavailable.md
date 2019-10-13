---
ms.openlocfilehash: 294c077b837899bd714deb2afd1bdff2b3185f38
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237407"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a><span data-ttu-id="0ba1f-101">Microsoft.VisualBasic.ApplicationServices 네임스페이스의 형식을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="0ba1f-101">Types in Microsoft.VisualBasic.ApplicationServices namespace not available</span></span>

<span data-ttu-id="0ba1f-102"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-102">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0ba1f-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0ba1f-103">Version introduced</span></span>

<span data-ttu-id="0ba1f-104">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="0ba1f-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="0ba1f-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0ba1f-105">Change description</span></span>

<span data-ttu-id="0ba1f-106">일부 .NET Core 3.0 미리 보기 릴리스에서는 <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-106">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="0ba1f-107">.NET Core 3.0 미리 보기 9부터는 해당 형식을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="0ba1f-108">후속 릴리스에서 불필요한 어셈블리 종속성이나 호환성이 손상되는 변경을 방지하기 위해 형식을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="0ba1f-109">권장 작업</span><span class="sxs-lookup"><span data-stu-id="0ba1f-109">Recommended action</span></span>

<span data-ttu-id="0ba1f-110">코드에서 <xref:Microsoft.VisualBasic.ApplicationServices> 형식과 해당 멤버를 사용해야 하는 경우, .NET 클래스 라이브러리의 해당 형식이나 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-110">If your code depends on the use of <xref:Microsoft.VisualBasic.ApplicationServices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="0ba1f-111">예를 들어 <xref:System.Environment?displayProperty=nameWithType> 및 <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>의 일부 멤버는 <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> 클래스의 속성과 동등한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba1f-111">For example, some <xref:System.Environment?displayProperty=nameWithType> and <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> members provide equivalent functionality to the properties of the <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> class.</span></span>

#### <a name="category"></a><span data-ttu-id="0ba1f-112">범주</span><span class="sxs-lookup"><span data-stu-id="0ba1f-112">Category</span></span>

<span data-ttu-id="0ba1f-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ba1f-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0ba1f-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0ba1f-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-- >

