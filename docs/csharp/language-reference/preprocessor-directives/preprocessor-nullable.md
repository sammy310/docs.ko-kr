---
description: '#nullable - C# 참조'
title: '#nullable - C# 참조'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099450"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="e5b4c-103">#nullable(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e5b4c-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="e5b4c-104">`#nullable` 전처리기 지시문은 ‘null 허용 주석 컨텍스트’ 및 ‘null 허용 경고 컨텍스트’를 설정합니다. </span><span class="sxs-lookup"><span data-stu-id="e5b4c-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="e5b4c-105">이 지시문은 null 허용 주석이 적용되는지와 null 허용 여부 경고가 지정되는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="e5b4c-106">각 컨텍스트는 *disabled* 또는 *enabled* 입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="e5b4c-107">두 컨텍스트 모두 프로젝트 수준(C# 소스 코드 외부)에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="e5b4c-108">`#nullable` 지시문은 주석 및 경고 컨텍스트를 제어하고 프로젝트 수준 설정보다 우선으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="e5b4c-109">지시문은 다른 지시문이 재정의할 때까지 제어하는 컨텍스트를 설정하거나 소스 파일의 끝까지 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="e5b4c-110">지시문의 효과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="e5b4c-111">`#nullable disable`: null 허용 주석 및 경고 컨텍스트를 *disabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="e5b4c-112">`#nullable enable`: null 허용 주석 및 경고 컨텍스트를 *enabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="e5b4c-113">`#nullable restore`: null 허용 주석 및 경고 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="e5b4c-114">`#nullable disable annotations`: null 허용 주석 컨텍스트를 *disabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="e5b4c-115">`#nullable enable annotations`: null 허용 주석 컨텍스트를 *enabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="e5b4c-116">`#nullable restore annotations`: null 허용 주석 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="e5b4c-117">`#nullable disable warnings`: null 허용 경고 컨텍스트를 *disabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="e5b4c-118">`#nullable enable warnings`: null 허용 경고 컨텍스트를 *enabled* 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="e5b4c-119">`#nullable restore warnings`: null 허용 경고 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b4c-120">참조</span><span class="sxs-lookup"><span data-stu-id="e5b4c-120">See also</span></span>

- [<span data-ttu-id="e5b4c-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e5b4c-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e5b4c-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e5b4c-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e5b4c-123">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="e5b4c-123">C# Preprocessor Directives</span></span>](./index.md)
