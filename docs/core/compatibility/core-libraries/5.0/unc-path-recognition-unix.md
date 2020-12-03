---
title: '호환성이 손상되는 변경: Unix에서 UNC 경로의 URI 인식'
description: Uri 클래스가 두 개의 슬래시로 시작하는 문자열을 Unix의 UNC 경로로 인식하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759639"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="f1625-103">Unix에서 UNC 경로의 URI 인식</span><span class="sxs-lookup"><span data-stu-id="f1625-103">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="f1625-104">이제 <xref:System.Uri> 클래스가 두 개의 슬래시(`//`)로 시작하는 문자열을 Unix 운영 체제의 UNC(범용 명명 규칙) 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-104">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="f1625-105">이 변경으로 인해 모든 플랫폼에서 해당 문자열에 대해 일관된 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-105">This change makes the behavior for such strings consistent across all platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="f1625-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f1625-106">Change description</span></span>

<span data-ttu-id="f1625-107">이전 버전의 .NET에서는 <xref:System.Uri> 클래스가 두 개의 슬래시로 시작하는 문자열(예: `//contoso`)을 Unix 운영 체제의 절대 파일 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-107">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="f1625-108">그러나 Windows에서는 해당 문자열이 UNC 경로로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-108">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="f1625-109">.NET 5.0부터 <xref:System.Uri> 클래스는 Unix를 비롯한 모든 플랫폼에서 두 개의 슬래시로 시작하는 문자열을 UNC 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-109">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="f1625-110">또한 속성이 UNC 의미 체계에 따라 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-110">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="f1625-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType>가 `true`를 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="f1625-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="f1625-112">경로의 백슬래시가 슬래시로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-112">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="f1625-113">예를 들어 `//first\second`는 `//first/second`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-113">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="f1625-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType>이 문자를 백분율 인코딩하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="f1625-115">예를 들어 `//first/\uFFF0`이 `//first/%EF%BF%B0`으로 변환되지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="f1625-115">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f1625-116">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f1625-116">Version introduced</span></span>

<span data-ttu-id="f1625-117">5.0</span><span class="sxs-lookup"><span data-stu-id="f1625-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f1625-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f1625-118">Recommended action</span></span>

<span data-ttu-id="f1625-119">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1625-119">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f1625-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f1625-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
