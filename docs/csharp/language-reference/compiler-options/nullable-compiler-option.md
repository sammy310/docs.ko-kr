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
ms.openlocfilehash: f9c6c204d2563865f741c6ddb4644eb56f956c12
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125048"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="2c823-103">-nullable(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="2c823-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="2c823-104">**-nullable** 옵션을 사용하여 원하는 null 허용 컨텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-104">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c823-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c823-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="2c823-106">인수</span><span class="sxs-lookup"><span data-stu-id="2c823-106">Arguments</span></span>

<span data-ttu-id="2c823-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2c823-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="2c823-108">`+` 또는 **-nullable**을 지정하면 컴파일러에서 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-108">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="2c823-109">`-`를 지정하면, 즉 실제로 **-nullable**을 지정하지 않으면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-109">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="2c823-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="2c823-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="2c823-111">null 허용 컨텍스트 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-111">Specifies the nullable context option.</span></span> <span data-ttu-id="2c823-112">`+` 또는 `-`와 비슷하게, 사용하거나 사용하지 않도록 설정하지만 null 허용 컨텍스트 특정성을 더 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="2c823-113">`enable` 인수를 사용하면 실제로 **-nullable**을 지정하는 것과 동일하며 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="2c823-114">`disable`을 지정하면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="2c823-115">`warnings` 인수를 제공하면( **-nullable:warnings**) null 허용 경고 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="2c823-116">`annotations` 인수를 지정하면 **-nullable:annotations**면 null 허용 주석 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c823-117">설명</span><span class="sxs-lookup"><span data-stu-id="2c823-117">Remarks</span></span>

<span data-ttu-id="2c823-118">흐름 분석은 실행 코드 내에서 변수의 Null 허용 여부를 유추하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="2c823-119">변수의 유추된 Null 허용 여부는 변수의 선언된 Null 허용 여부와 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="2c823-120">메서드 호출은 조건부로 생략된 경우에도 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-120">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="2c823-121">예를 들어 릴리스 모드의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="2c823-122">다음 특성으로 주석이 지정된 메서드를 호출하면 흐름 분석에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="2c823-123">간단한 사전 조건: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="2c823-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="2c823-124">간단한 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="2c823-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="2c823-125">조건부 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="2c823-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="2c823-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(예: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>에 대한 `DoesNotReturnIf(false)`) 및 <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="2c823-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="2c823-127">멤버 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> 및 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="2c823-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="2c823-128">프로젝트에서 이 컴파일러 옵션을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="2c823-128">To set this compiler option in a project</span></span>

<span data-ttu-id="2c823-129">다음과 같이 *.csproj* 파일을 편집하여 `Project/PropertyGroup` 계층 구조 내에 `<Nullable>` 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2c823-129">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="2c823-130">참조</span><span class="sxs-lookup"><span data-stu-id="2c823-130">See also</span></span>

- [<span data-ttu-id="2c823-131">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="2c823-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="2c823-132">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="2c823-132">Nullable reference types</span></span>](../../nullable-references.md)
