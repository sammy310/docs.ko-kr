---
title: '호환성이 손상되는 변경: CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.'
description: 코드 분석 규칙 CA2013 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: fc68d9a3af0d629dc39aba0091d32b1982d6f2c5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257767"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="71191-103">경고 CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="71191-103">Warning CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="71191-104">.NET 코드 분석기 규칙 [CA2013](/visualstudio/code-quality/ca2013)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71191-104">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="71191-105"><xref:System.Object.ReferenceEquals(System.Object,System.Object)>를 사용하여 하나 이상의 값 형식이 같은지 비교하는 코드에 대한 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="71191-105">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

## <a name="change-description"></a><span data-ttu-id="71191-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="71191-106">Change description</span></span>

<span data-ttu-id="71191-107">.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71191-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="71191-108">[CA2013](/visualstudio/code-quality/ca2013)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71191-108">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="71191-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71191-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="71191-110">규칙 CA2013은 <xref:System.Object.ReferenceEquals(System.Object,System.Object)>를 사용하여 하나 이상의 값 형식이 같은지 비교하는 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="71191-110">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="71191-111">이런 방식으로 값 형식이 같은지 비교하면 비교되기 전에 값이 boxing되므로 잘못된 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71191-111">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="71191-112">비교된 값이 동일한 값 형식 인스턴스를 나타내는 경우에도 <xref:System.Object.ReferenceEquals(System.Object,System.Object)>는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71191-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="71191-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="71191-113">Version introduced</span></span>

<span data-ttu-id="71191-114">5.0</span><span class="sxs-lookup"><span data-stu-id="71191-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="71191-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="71191-115">Recommended action</span></span>

- <span data-ttu-id="71191-116">`==` 등의 적절한 같음 연산자를 사용하도록 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="71191-116">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="71191-117">이 경고는 표시하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71191-117">You should not suppress this warning.</span></span>

- <span data-ttu-id="71191-118">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="71191-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="71191-119">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71191-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="71191-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="71191-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
