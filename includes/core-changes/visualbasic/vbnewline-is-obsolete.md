---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117112"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="3aa2e-101">Microsoft.VisualBasic.Constants.vbNewLine은 사용되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="3aa2e-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="3aa2e-102"><xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수는 .NET Framework에서 [Obsolete](xref:System.ObsoleteAttribute)로 표시되지만 이 특성은 이전에 .NET Core 3.0 라이브러리에서 누락되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3aa2e-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3aa2e-103">Version introduced</span></span>

<span data-ttu-id="3aa2e-104">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="3aa2e-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="3aa2e-105">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3aa2e-105">Details</span></span>

<span data-ttu-id="3aa2e-106">.NET Core 3.0 미리 보기 8부터 [Obsolete](xref:System.ObsoleteAttribute) 특성은 .NET Framework에서 `vbNewLine`을 준수하기 위해 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 상수에 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="3aa2e-107">`vbNewLine` 상수를 사용하면 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="3aa2e-108">이전 버전의 .NET Core에서는 `vbNewLine`이 컴파일러 경고를 생성하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3aa2e-109">권장 작업</span><span class="sxs-lookup"><span data-stu-id="3aa2e-109">Recommended action</span></span>

<span data-ttu-id="3aa2e-110">`vbNewLine`의 [Obsolete](xref:System.ObsoleteAttribute) 특성 메시지에는 다음 권장 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="3aa2e-111">캐리지 리턴 및 줄 바꿈의 경우 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="3aa2e-112">현재 플랫폼의 줄 바꿈의 경우 <xref:System.Environment.NewLine?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2e-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="3aa2e-113">범주</span><span class="sxs-lookup"><span data-stu-id="3aa2e-113">Category</span></span>

<span data-ttu-id="3aa2e-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3aa2e-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3aa2e-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3aa2e-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

