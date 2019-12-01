---
ms.openlocfilehash: 86cdb845c436f424bbcc70e0736568031143b204
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567445"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="722bf-101">Microsoft.VisualBasic.Constants.vbNewLine은 사용되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="722bf-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="722bf-102"><xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수는 .NET Core 3.0 미리 보기 8부터 [사용되지 않음](xref:System.ObsoleteAttribute)으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="722bf-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="722bf-103">Version introduced</span></span>

<span data-ttu-id="722bf-104">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="722bf-104">3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="722bf-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="722bf-105">Change description</span></span>

<span data-ttu-id="722bf-106">.NET Core 3.0 미리 보기 8부터 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수에 [Obsolete](xref:System.ObsoleteAttribute) 특성이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="722bf-107">이 상수를 사용하면 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="722bf-108">.NET Core 및 .NET Framework의 이전 릴리스에서는 사용되지 않음으로 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-108">In previous releases of both .NET Core and .NET Framework, it was not marked as obsolete.</span></span>

<span data-ttu-id="722bf-109">이 변경은 다중 플랫폼 개발 언어로 Visual Basic을 지원하기 위해 적용된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="722bf-110">`vbNewLine` 상수는 Windows의 줄 바꿈 문자 시퀀스인 `\r\n`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-110">The `vbNewLine` constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="722bf-111">Unix 기반 시스템에서 줄 바꿈 문자는 `\n`입니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="722bf-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="722bf-112">Recommended action</span></span>

<span data-ttu-id="722bf-113">`vbNewLine`의 [Obsolete](xref:System.ObsoleteAttribute) 특성 메시지에는 다음 권장 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="722bf-114">캐리지 리턴 및 줄 바꿈의 경우 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-114">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="722bf-115">현재 플랫폼의 줄 바꿈의 경우 <xref:System.Environment.NewLine?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="722bf-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="722bf-116">범주</span><span class="sxs-lookup"><span data-stu-id="722bf-116">Category</span></span>

<span data-ttu-id="722bf-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="722bf-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="722bf-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="722bf-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
