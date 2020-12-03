---
title: '호환성이 손상되는 변경: Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨'
description: Environment.OSVersion이 애플리케이션 호환성을 위해 선택된 OS 대신 운영 체제의 실제 버전을 반환하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760072"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="fc56e-103">Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨</span><span class="sxs-lookup"><span data-stu-id="fc56e-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="fc56e-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 애플리케이션 호환성을 위해 선택된 OS 등이 아닌 실제 OS(운영 체제) 버전이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="fc56e-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="fc56e-105">Change description</span></span>

<span data-ttu-id="fc56e-106">이전 .NET 버전에서는 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows 호환 모드에서 애플리케이션을 실행할 경우 부정확할 수 있는 OS 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="fc56e-107">자세한 내용은 [GetVersionExA 함수 설명](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc56e-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="fc56e-108">.NET 5.0부터 <xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 실제 운영 체제 버전이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-108">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="fc56e-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="fc56e-109">Reason for change</span></span>

<span data-ttu-id="fc56e-110">이 속성의 사용자는 실제 운영 체제 버전이 반환될 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-110">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="fc56e-111">대부분의 .NET 앱은 애플리케이션 매니페스트에서 지원되는 버전을 지정하지 않으므로 dotnet 호스트에서 지원되는 기본 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-111">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="fc56e-112">따라서 호환성 shim은 실행 중인 앱에서 거의 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-112">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="fc56e-113">Windows에서 새 버전을 릴리스할 때 이전 dotnet 호스트를 아직 사용 중인 경우 해당 앱이 잘못된 OS 버전을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-113">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="fc56e-114">실제 버전을 반환하는 것이 이 API에 대한 개발자의 기대와 좀 더 부합됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-114">Returning the actual version is more inline with developers' expectations of this API.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="fc56e-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fc56e-115">Version introduced</span></span>

<span data-ttu-id="fc56e-116">5.0</span><span class="sxs-lookup"><span data-stu-id="fc56e-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fc56e-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="fc56e-117">Recommended action</span></span>

<span data-ttu-id="fc56e-118"><xref:System.Environment.OSVersion?displayProperty=nameWithType>을 사용하는 코드를 검토하고 테스트하여 원하는 대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc56e-118">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fc56e-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fc56e-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
