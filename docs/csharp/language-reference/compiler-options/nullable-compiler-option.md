---
description: -nullable(C# 컴파일러 옵션)
title: -nullable(C# 컴파일러 옵션)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099226"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="35ea7-103">-nullable(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="35ea7-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="35ea7-104">**-nullable** 옵션을 사용하여 null 허용 컨텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="35ea7-105">구문</span><span class="sxs-lookup"><span data-stu-id="35ea7-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="35ea7-106">인수</span><span class="sxs-lookup"><span data-stu-id="35ea7-106">Arguments</span></span>

<span data-ttu-id="35ea7-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="35ea7-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="35ea7-108">`+` 또는 **-nullable** 을 지정하면 컴파일러에서 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="35ea7-109">**-nullable** 을 지정하지 않을 경우 적용되는 `-`를 지정하면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="35ea7-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="35ea7-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="35ea7-111">null 허용 컨텍스트 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-111">Specifies the nullable context option.</span></span> <span data-ttu-id="35ea7-112">`+` 또는 `-`와 비슷하게, 사용하거나 사용하지 않도록 설정하지만 null 허용 컨텍스트 특정성을 더 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="35ea7-113">`enable` 인수를 사용하면 실제로 **-nullable** 을 지정하는 것과 동일하며 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="35ea7-114">`disable`을 지정하면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="35ea7-115">`warnings` 인수를 제공하면( **-nullable:warnings**) null 허용 경고 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="35ea7-116">`annotations` 인수를 지정하면 **-nullable:annotations** 면 null 허용 주석 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="35ea7-117">설명</span><span class="sxs-lookup"><span data-stu-id="35ea7-117">Remarks</span></span>

<span data-ttu-id="35ea7-118">흐름 분석은 실행 코드 내에서 변수의 Null 허용 여부를 유추하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="35ea7-119">변수의 유추된 Null 허용 여부는 변수의 선언된 Null 허용 여부와 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="35ea7-120">메서드 호출은 조건부로 생략된 경우에도 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="35ea7-121">예를 들어 릴리스 모드의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="35ea7-122">다음 특성으로 주석이 지정된 메서드를 호출하면 흐름 분석에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="35ea7-123">간단한 사전 조건: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="35ea7-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="35ea7-124">간단한 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="35ea7-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="35ea7-125">조건부 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="35ea7-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="35ea7-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(예: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>에 대한 `DoesNotReturnIf(false)`) 및 <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="35ea7-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="35ea7-127">멤버 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> 및 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="35ea7-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="35ea7-128">전역 null 허용 컨텍스트는 생성된 코드 파일에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="35ea7-129">이 설정과 관계없이 null 허용 컨텍스트는 생성됨으로 표시된 모든 소스 파일에 대해 *disabled* 입니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="35ea7-130">다음 네 가지 방법으로 파일은 생성됨으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="35ea7-131">.editorconfig에서 해당 파일에 적용되는 섹션에 `generated_code = true`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="35ea7-132">파일의 맨 위에 있는 주석에 `<auto-generated>` 또는 `<auto-generated/>`를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="35ea7-133">해당 주석의 모든 줄에 넣을 수 있지만 주석 블록은 파일의 첫 번째 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="35ea7-134">파일 이름을 *TemporaryGeneratedFile_* 로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="35ea7-135">파일 이름을 *.designer.cs*, *.generated.cs*, *.g.cs* 또는 *.g.i.cs* 로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="35ea7-136">생성기는 [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) 전처리기 지시문을 사용하여 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="35ea7-137">프로젝트에서 이 컴파일러 옵션을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="35ea7-137">To set this compiler option in a project</span></span>

<span data-ttu-id="35ea7-138">다음과 같이 *.csproj* 파일을 편집하여 `Project/PropertyGroup` 계층 구조 내에 `<Nullable>` 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="35ea7-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="35ea7-139">참조</span><span class="sxs-lookup"><span data-stu-id="35ea7-139">See also</span></span>

- [<span data-ttu-id="35ea7-140">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="35ea7-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="35ea7-141">`#nullable` 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="35ea7-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="35ea7-142">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="35ea7-142">Nullable reference types</span></span>](../../nullable-references.md)
