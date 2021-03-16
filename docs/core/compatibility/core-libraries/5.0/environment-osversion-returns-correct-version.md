---
title: '호환성이 손상되는 변경: Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨'
description: Environment.OSVersion이 애플리케이션 호환성을 위해 선택된 OS 대신 운영 체제의 실제 버전을 반환하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 05ec886061263ea43a2d956b8ce0ecc06e2bf3ad
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257533"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="d8215-103">Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨</span><span class="sxs-lookup"><span data-stu-id="d8215-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="d8215-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 애플리케이션 호환성을 위해 선택된 OS 등이 아닌 실제 OS(운영 체제) 버전이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="d8215-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d8215-105">Change description</span></span>

<span data-ttu-id="d8215-106">이전 .NET 버전에서는 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows 호환 모드에서 애플리케이션을 실행할 경우 부정확할 수 있는 OS 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="d8215-107">자세한 내용은 [GetVersionExA 함수 설명](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8215-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span> <span data-ttu-id="d8215-108">macOS에서 <xref:System.Environment.OSVersion?displayProperty=nameWithType>은 기본 Darwin 커널 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-108">On macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the underlying Darwin kernel version.</span></span>

<span data-ttu-id="d8215-109">.NET 5부터 <xref:System.Environment.OSVersion?displayProperty=nameWithType>은 Windows와 macOS의 실제 운영 체제 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-109">Starting in .NET 5, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system for Windows and macOS.</span></span>

<span data-ttu-id="d8215-110">다음 표에는 동작에서의 차이가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-110">The following table shows the difference in behavior.</span></span>

|  | <span data-ttu-id="d8215-111">이전 .NET 버전</span><span class="sxs-lookup"><span data-stu-id="d8215-111">Previous .NET versions</span></span> | <span data-ttu-id="d8215-112">.NET 5 이상</span><span class="sxs-lookup"><span data-stu-id="d8215-112">.NET 5+</span></span> |
|--|------------------------|---------|
| <span data-ttu-id="d8215-113">Windows</span><span class="sxs-lookup"><span data-stu-id="d8215-113">Windows</span></span> | <span data-ttu-id="d8215-114">6.2.9200.0</span><span class="sxs-lookup"><span data-stu-id="d8215-114">6.2.9200.0</span></span> | <span data-ttu-id="d8215-115">10.0.19042.0</span><span class="sxs-lookup"><span data-stu-id="d8215-115">10.0.19042.0</span></span> |
| <span data-ttu-id="d8215-116">macOS</span><span class="sxs-lookup"><span data-stu-id="d8215-116">macOS</span></span> | <span data-ttu-id="d8215-117">19.6.0.0</span><span class="sxs-lookup"><span data-stu-id="d8215-117">19.6.0.0</span></span> | <span data-ttu-id="d8215-118">10.15.7</span><span class="sxs-lookup"><span data-stu-id="d8215-118">10.15.7</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="d8215-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d8215-119">Reason for change</span></span>

<span data-ttu-id="d8215-120">이 속성의 사용자는 실제 운영 체제 버전이 반환될 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-120">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="d8215-121">대부분의 .NET 앱은 애플리케이션 매니페스트에서 지원되는 버전을 지정하지 않으므로 dotnet 호스트에서 지원되는 기본 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-121">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="d8215-122">따라서 호환성 shim은 실행 중인 앱에서 거의 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-122">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="d8215-123">Windows에서 새 버전을 릴리스할 때 이전 dotnet 호스트를 아직 사용 중인 경우 해당 앱이 잘못된 OS 버전을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-123">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="d8215-124">실제 버전을 반환하는 것이 이 API에 대한 개발자의 기대와 좀 더 부합됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-124">Returning the actual version is more inline with developers' expectations of this API.</span></span>

<span data-ttu-id="d8215-125">.NET 5에서 <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType>가 도입되어 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows와 macOS에 일관성 있게 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-125">With the introduction of <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType>, and <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5, <xref:System.Environment.OSVersion?displayProperty=nameWithType> was changed to be consistent for Windows and macOS.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d8215-126">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d8215-126">Version introduced</span></span>

<span data-ttu-id="d8215-127">5.0</span><span class="sxs-lookup"><span data-stu-id="d8215-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d8215-128">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d8215-128">Recommended action</span></span>

<span data-ttu-id="d8215-129"><xref:System.Environment.OSVersion?displayProperty=nameWithType>을 사용하는 코드를 검토하고 테스트하여 원하는 대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8215-129">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d8215-130">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d8215-130">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
