---
ms.openlocfilehash: 09027863ff2f0009a14578db35db870c27369726
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721775"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a><span data-ttu-id="bfa38-101">Microsoft.VisualBasic.ApplicationServices 네임스페이스의 형식을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="bfa38-101">Types in Microsoft.VisualBasic.ApplicationServices namespace not available</span></span>

<span data-ttu-id="bfa38-102"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-102">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bfa38-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bfa38-103">Version introduced</span></span>

<span data-ttu-id="bfa38-104">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="bfa38-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="bfa38-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="bfa38-105">Change description</span></span>

<span data-ttu-id="bfa38-106">일부 .NET Core 3.0 미리 보기 릴리스에서는 <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-106">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="bfa38-107">.NET Core 3.0 미리 보기 9부터는 해당 형식을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="bfa38-108">후속 릴리스에서 불필요한 어셈블리 종속성이나 호환성이 손상되는 변경을 방지하기 위해 형식을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bfa38-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bfa38-109">Recommended action</span></span>

<span data-ttu-id="bfa38-110">코드에서 <xref:Microsoft.VisualBasic.ApplicationServices> 형식과 해당 멤버를 사용해야 하는 경우, .NET 클래스 라이브러리의 해당 형식이나 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-110">If your code depends on the use of <xref:Microsoft.VisualBasic.ApplicationServices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="bfa38-111">예를 들어 <xref:System.Environment?displayProperty=nameWithType> 및 <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>의 일부 멤버는 <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> 클래스의 속성과 동등한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa38-111">For example, some <xref:System.Environment?displayProperty=nameWithType> and <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> members provide equivalent functionality to the properties of the <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> class.</span></span>

#### <a name="category"></a><span data-ttu-id="bfa38-112">범주</span><span class="sxs-lookup"><span data-stu-id="bfa38-112">Category</span></span>

<span data-ttu-id="bfa38-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfa38-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bfa38-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bfa38-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
