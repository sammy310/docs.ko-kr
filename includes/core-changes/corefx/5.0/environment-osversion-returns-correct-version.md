---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558185"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="3a2bd-101">Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨</span><span class="sxs-lookup"><span data-stu-id="3a2bd-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="3a2bd-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 애플리케이션 호환성을 위해 선택된 OS 등이 아닌 실제 OS(운영 체제) 버전이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3a2bd-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3a2bd-103">Change description</span></span>

<span data-ttu-id="3a2bd-104">이전 .NET 버전에서는 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows 호환 모드에서 애플리케이션을 실행할 경우 부정확할 수 있는 OS 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="3a2bd-105">자세한 내용은 [GetVersionExA 함수 설명](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="3a2bd-106">.NET 5.0부터 <xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 실제 운영 체제 버전이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3a2bd-107">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3a2bd-107">Reason for change</span></span>

<span data-ttu-id="3a2bd-108">이 속성의 사용자는 실제 운영 체제 버전이 반환될 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="3a2bd-109">대부분의 .NET 앱은 애플리케이션 매니페스트에서 지원되는 버전을 지정하지 않으므로 dotnet 호스트에서 지원되는 기본 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="3a2bd-110">따라서 호환성 shim은 실행 중인 앱에서 거의 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="3a2bd-111">Windows에서 새 버전을 릴리스할 때 이전 dotnet 호스트를 아직 사용 중인 경우 해당 앱이 잘못된 OS 버전을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="3a2bd-112">실제 버전을 반환하는 것이 이 API에 대한 개발자의 기대와 좀 더 부합됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3a2bd-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3a2bd-113">Version introduced</span></span>

<span data-ttu-id="3a2bd-114">5.0</span><span class="sxs-lookup"><span data-stu-id="3a2bd-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3a2bd-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3a2bd-115">Recommended action</span></span>

<span data-ttu-id="3a2bd-116"><xref:System.Environment.OSVersion?displayProperty=nameWithType>을 사용하는 코드를 검토하고 테스트하여 원하는 대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3a2bd-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="3a2bd-117">범주</span><span class="sxs-lookup"><span data-stu-id="3a2bd-117">Category</span></span>

<span data-ttu-id="3a2bd-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3a2bd-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a2bd-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3a2bd-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
