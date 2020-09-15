---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617208"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="99d5a-101">System.Uri 구문 분석이 RFC 3987을 준수</span><span class="sxs-lookup"><span data-stu-id="99d5a-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="99d5a-102">설명</span><span class="sxs-lookup"><span data-stu-id="99d5a-102">Details</span></span>

<span data-ttu-id="99d5a-103">.NET Framework 4.5에서 URI 구문 분석은 여러 방법으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="99d5a-104">단, 이러한 변경 내용은 .NET Framework 4.5를 대상으로 하는 코드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="99d5a-105">이진 파일이 .NET Framework 4.0을 대상으로 하는 경우, 이전 동작이 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="99d5a-106">.NET Framework 4.5의 URI 구문 분석 변경 내용은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="99d5a-107">URI 구문 분석은 RFC 3987의 최신 IRI 규칙에 따라 정규화 및 문자 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="99d5a-108">유니코드 정규화 형식 C는 URI의 호스트 부분에서만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="99d5a-109">잘못된 mailto: URI가 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="99d5a-110">이제 패스 세그먼트 끝의 후행 점이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="99d5a-111">`file://` URI는 `?` 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="99d5a-112">유니코드 제어 문자 `U+0080`에서 `U+009F`는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="99d5a-113">쉼표 문자 `,` 또는 `%2c`는 자동으로 이스케이프가 해제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="99d5a-114">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="99d5a-114">Suggestion</span></span>

<span data-ttu-id="99d5a-115">이전 .NET Framework 4.0 URI 구문 분석 의미 체계가 필요한 경우(주로 필요하지 않음) .NET Framework 4.0을 대상으로 하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="99d5a-116">이것은 어셈블리에서 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>를 사용하거나 '프로젝트 속성' 페이지에서 Visual Studio의 프로젝트 시스템 UI를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99d5a-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="99d5a-117">이름</span><span class="sxs-lookup"><span data-stu-id="99d5a-117">Name</span></span>    | <span data-ttu-id="99d5a-118">값</span><span class="sxs-lookup"><span data-stu-id="99d5a-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="99d5a-119">Scope</span><span class="sxs-lookup"><span data-stu-id="99d5a-119">Scope</span></span>   | <span data-ttu-id="99d5a-120">주요함</span><span class="sxs-lookup"><span data-stu-id="99d5a-120">Major</span></span>       |
| <span data-ttu-id="99d5a-121">버전</span><span class="sxs-lookup"><span data-stu-id="99d5a-121">Version</span></span> | <span data-ttu-id="99d5a-122">4.5</span><span class="sxs-lookup"><span data-stu-id="99d5a-122">4.5</span></span>         |
| <span data-ttu-id="99d5a-123">형식</span><span class="sxs-lookup"><span data-stu-id="99d5a-123">Type</span></span>    | <span data-ttu-id="99d5a-124">대상 변경</span><span class="sxs-lookup"><span data-stu-id="99d5a-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="99d5a-125">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="99d5a-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
