---
title: '호환성이 손상되는 변경: 단일 파일 게시 형식에 대한 어셈블리 관련 API 동작 변경'
description: 단일 파일 게시 형식으로 호출될 때 어셈블리의 파일 위치와 관련된 여러 API의 동작이 변경되는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 3810a71fac481a42ccf2c8e64149d171f31c6821
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257689"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="7a619-103">단일 파일 게시 형식에 대한 어셈블리 관련 API 동작 변경</span><span class="sxs-lookup"><span data-stu-id="7a619-103">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="7a619-104">단일 파일 게시 형식으로 호출된 경우 어셈블리의 파일 위치와 관련된 여러 API의 동작이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-104">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

## <a name="change-description"></a><span data-ttu-id="7a619-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7a619-105">Change description</span></span>

<span data-ttu-id="7a619-106">.NET 5 이상 버전의 단일 파일 게시에서는 번들 어셈블리가 디스크에 추출되는 대신 메모리에서 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-106">In single-file publishing for .NET 5 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="7a619-107">이로 인해 단일 파일 게시 앱의 경우 .NET 5 이상과 이전 버전의 .NET에서 특정 위치 관련 API를 통해 반환되는 값이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-107">For single-file published apps, this means that certain location-related APIs return different values on .NET 5 and later than on previous versions of .NET.</span></span> <span data-ttu-id="7a619-108">변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-108">The changes are as follows:</span></span>

| <span data-ttu-id="7a619-109">API</span><span class="sxs-lookup"><span data-stu-id="7a619-109">API</span></span> | <span data-ttu-id="7a619-110">이전 버전</span><span class="sxs-lookup"><span data-stu-id="7a619-110">Previous versions</span></span> | <span data-ttu-id="7a619-111">.NET 5 이상</span><span class="sxs-lookup"><span data-stu-id="7a619-111">.NET 5 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="7a619-112">추출된 DLL 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="7a619-113">번들 어셈블리에 대해 빈 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-113">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="7a619-114">추출된 DLL 파일 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-114">Returns extracted DLL file path</span></span> | <span data-ttu-id="7a619-115">번들 어셈블리에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-115">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7a619-116">번들 어셈블리에 대해 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-116">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="7a619-117">번들 어셈블리에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-117">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="7a619-118">값은 진입점 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-118">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="7a619-119">값은 호스트 실행 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-119">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="7a619-120">값은 임시 추출 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-120">Value is the temporary extraction directory</span></span> | <span data-ttu-id="7a619-121">값은 호스트 실행 파일을 포함하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-121">Value is the containing directory of the host executable</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="7a619-122">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7a619-122">Version introduced</span></span>

<span data-ttu-id="7a619-123">5.0</span><span class="sxs-lookup"><span data-stu-id="7a619-123">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7a619-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7a619-124">Recommended action</span></span>

<span data-ttu-id="7a619-125">단일 파일로 게시하는 경우 어셈블리 파일 위치에 대한 종속성을 피합니다.</span><span class="sxs-lookup"><span data-stu-id="7a619-125">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7a619-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7a619-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
