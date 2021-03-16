---
title: '호환성이 손상되는 변경: CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함'
description: 코드 분석 규칙 CA2247 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: 6c7accaad312352a1448406f2bbf4189f3df1ee5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257702"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="7566a-103">경고 CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함</span><span class="sxs-lookup"><span data-stu-id="7566a-103">Warning CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="7566a-104">.NET 코드 분석기 규칙 [CA2247](/visualstudio/code-quality/ca2247)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-104">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="7566a-105"><xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출에 대한 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-105">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

## <a name="change-description"></a><span data-ttu-id="7566a-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7566a-106">Change description</span></span>

<span data-ttu-id="7566a-107">.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="7566a-108">[CA2247](/visualstudio/code-quality/ca2247)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-108">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="7566a-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="7566a-110">규칙 CA2247은 <xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-110">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="7566a-111"><xref:System.Threading.Tasks.TaskCompletionSource%601> 형식에는 <xref:System.Threading.Tasks.TaskCreationOptions> 값을 허용하는 생성자와 <xref:System.Object>를 허용하는 다른 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-111">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="7566a-112"><xref:System.Threading.Tasks.TaskCreationOptions> 값 대신 <xref:System.Threading.Tasks.TaskContinuationOptions> 값을 실수로 전달하는 경우 <xref:System.Object> 매개 변수를 사용하는 생성자가 런타임에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-112">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="7566a-113">코드가 컴파일되어 실행되지만 의도한 동작이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-113">Your code will compile and run but won't have the intended behavior.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7566a-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7566a-114">Version introduced</span></span>

<span data-ttu-id="7566a-115">5.0</span><span class="sxs-lookup"><span data-stu-id="7566a-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7566a-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7566a-116">Recommended action</span></span>

- <span data-ttu-id="7566a-117"><xref:System.Threading.Tasks.TaskContinuationOptions> 인수를 해당하는 <xref:System.Threading.Tasks.TaskCreationOptions> 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-117">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="7566a-118">코드의 버그를 대부분 강조 표시하므로 이 경고를 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-118">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="7566a-119">자세한 내용은 [CA2247](/visualstudio/code-quality/ca2247)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7566a-119">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="7566a-120">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7566a-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="7566a-121">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7566a-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7566a-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7566a-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
