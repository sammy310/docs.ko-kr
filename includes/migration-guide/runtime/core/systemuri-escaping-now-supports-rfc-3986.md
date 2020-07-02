---
ms.openlocfilehash: 1d7dc808d5b514acc582675d6ccdbd5778314624
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620266"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="74dd1-101">이제 System.Uri 이스케이프가 RFC 3986을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="74dd1-102">설명</span><span class="sxs-lookup"><span data-stu-id="74dd1-102">Details</span></span>

<span data-ttu-id="74dd1-103">.NET Framework 4.5에서 URI 이스케이프가 [RFC 3986](https://tools.ietf.org/html/rfc3986)을 지원하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="74dd1-104">특정 변경 내용은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-104">Specific changes include:</span></span><ul><li><span data-ttu-id="74dd1-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName>은 RFC 3986을 기반으로 하는 예약된 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="74dd1-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName>은 예약된 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="74dd1-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName>은 잘못된 이스케이프 시퀀스가 발생하는 경우 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="74dd1-108">예약되지 않은 이스케이프된 문자는 이스케이프 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="74dd1-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="74dd1-109">Suggestion</span></span>

<ul><li><span data-ttu-id="74dd1-110">잘못된 이스케이프 시퀀스의 경우 throw하여 애플리케이션이 <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName>을 의존하지 않도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="74dd1-111">이제 이러한 시퀀스를 직접 발견해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="74dd1-112">마찬가지로, 이스케이프되거나 이스케이프되지 않은 URI 및 데이터 문자열이 .NET Framework 4.0과 .NET Framework 4.5에서 달라질 수 있으며 .NET 버전 간에 직접 비교되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="74dd1-113">대신 어떤 비교도 실행되기 전에 단일 .NET 버전에 구문 분석되고 표준화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dd1-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="74dd1-114">이름</span><span class="sxs-lookup"><span data-stu-id="74dd1-114">Name</span></span>    | <span data-ttu-id="74dd1-115">값</span><span class="sxs-lookup"><span data-stu-id="74dd1-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="74dd1-116">Scope</span><span class="sxs-lookup"><span data-stu-id="74dd1-116">Scope</span></span>   |<span data-ttu-id="74dd1-117">부</span><span class="sxs-lookup"><span data-stu-id="74dd1-117">Minor</span></span>|
|<span data-ttu-id="74dd1-118">버전</span><span class="sxs-lookup"><span data-stu-id="74dd1-118">Version</span></span>|<span data-ttu-id="74dd1-119">4.5</span><span class="sxs-lookup"><span data-stu-id="74dd1-119">4.5</span></span>|
|<span data-ttu-id="74dd1-120">형식</span><span class="sxs-lookup"><span data-stu-id="74dd1-120">Type</span></span>|<span data-ttu-id="74dd1-121">런타임</span><span class="sxs-lookup"><span data-stu-id="74dd1-121">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74dd1-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="74dd1-122">Affected APIs</span></span>

-<xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
