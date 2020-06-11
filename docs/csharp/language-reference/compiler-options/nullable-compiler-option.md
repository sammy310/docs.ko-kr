---
title: -nullable(C# 컴파일러 옵션)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449800"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="73cba-102">-nullable(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="73cba-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="73cba-103">**-nullable** 옵션을 사용하여 원하는 null 허용 컨텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="73cba-104">구문</span><span class="sxs-lookup"><span data-stu-id="73cba-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="73cba-105">인수</span><span class="sxs-lookup"><span data-stu-id="73cba-105">Arguments</span></span>

<span data-ttu-id="73cba-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="73cba-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="73cba-107">`+` 또는 **-nullable**을 지정하면 컴파일러에서 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="73cba-108">`-`를 지정하면, 즉 실제로 **-nullable**을 지정하지 않으면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="73cba-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="73cba-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="73cba-110">null 허용 컨텍스트 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-110">Specifies the nullable context option.</span></span> <span data-ttu-id="73cba-111">`+` 또는 `-`와 비슷하게, 사용하거나 사용하지 않도록 설정하지만 null 허용 컨텍스트 특정성을 더 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="73cba-112">`enable` 인수를 사용하면 실제로 **-nullable**을 지정하는 것과 동일하며 null 허용 컨텍스트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="73cba-113">`disable`을 지정하면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="73cba-114">`warnings` 인수를 제공하면( **-nullable:warnings**) null 허용 경고 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="73cba-115">`annotations` 인수를 지정하면 **-nullable:annotations**면 null 허용 주석 컨텍스트가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="73cba-116">설명</span><span class="sxs-lookup"><span data-stu-id="73cba-116">Remarks</span></span>

<span data-ttu-id="73cba-117">흐름 분석은 실행 코드 내에서 변수의 Null 허용 여부를 유추하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="73cba-118">변수의 유추된 Null 허용 여부는 변수의 선언된 Null 허용 여부와 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="73cba-119">메서드 호출은 조건부로 생략된 경우에도 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="73cba-120">예를 들어 릴리스 모드의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="73cba-121">다음 특성으로 주석이 지정된 메서드를 호출하면 흐름 분석에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="73cba-122">간단한 사전 조건: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="73cba-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="73cba-123">간단한 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="73cba-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="73cba-124">조건부 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="73cba-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="73cba-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(예: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>의 경우 `DoesNotReturnIf(false)`) 및 <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="73cba-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (e.g. `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="73cba-126">멤버 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> 및 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="73cba-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="73cba-127">프로젝트에서 이 컴파일러 옵션을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="73cba-127">To set this compiler option in a project</span></span>

<span data-ttu-id="73cba-128">다음과 같이 *.csproj*를 편집하여 `Project/PropertyGroup` 계층 구조 내에 `<Nullable>` 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73cba-128">Edit the *.csproj* to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="73cba-129">참조</span><span class="sxs-lookup"><span data-stu-id="73cba-129">See also</span></span>

- [<span data-ttu-id="73cba-130">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="73cba-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="73cba-131">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="73cba-131">Nullable reference types</span></span>](../../nullable-references.md)
