---
title: sizeof - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422403"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="ec327-102">sizeof(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ec327-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="ec327-103">관리되지 않는 형식의 크기(바이트)를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="ec327-104">관리되지 않는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-104">Unmanaged types include:</span></span>

- <span data-ttu-id="ec327-105">다음 표에서는 간단한 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="ec327-106">식</span><span class="sxs-lookup"><span data-stu-id="ec327-106">Expression</span></span>|<span data-ttu-id="ec327-107">상수 값</span><span class="sxs-lookup"><span data-stu-id="ec327-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="ec327-108">1</span><span class="sxs-lookup"><span data-stu-id="ec327-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="ec327-109">1</span><span class="sxs-lookup"><span data-stu-id="ec327-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="ec327-110">2</span><span class="sxs-lookup"><span data-stu-id="ec327-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="ec327-111">2</span><span class="sxs-lookup"><span data-stu-id="ec327-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="ec327-112">4</span><span class="sxs-lookup"><span data-stu-id="ec327-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="ec327-113">4</span><span class="sxs-lookup"><span data-stu-id="ec327-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="ec327-114">8</span><span class="sxs-lookup"><span data-stu-id="ec327-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="ec327-115">8</span><span class="sxs-lookup"><span data-stu-id="ec327-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="ec327-116">2(유니코드)</span><span class="sxs-lookup"><span data-stu-id="ec327-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="ec327-117">4</span><span class="sxs-lookup"><span data-stu-id="ec327-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="ec327-118">8</span><span class="sxs-lookup"><span data-stu-id="ec327-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="ec327-119">16</span><span class="sxs-lookup"><span data-stu-id="ec327-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="ec327-120">1</span><span class="sxs-lookup"><span data-stu-id="ec327-120">1</span></span>|

- <span data-ttu-id="ec327-121">열거형 형식.</span><span class="sxs-lookup"><span data-stu-id="ec327-121">Enum types.</span></span>

- <span data-ttu-id="ec327-122">포인터 형식.</span><span class="sxs-lookup"><span data-stu-id="ec327-122">Pointer types.</span></span>

- <span data-ttu-id="ec327-123">참조 형식 또는 구성된 형식인 모든 인스턴스 필드 또는 자동 구현 인스턴스 속성을 포함하지 않는 사용자 정의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="ec327-124">다음 예제에서는 `int`의 크기를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="ec327-125">주의</span><span class="sxs-lookup"><span data-stu-id="ec327-125">Remarks</span></span>

<span data-ttu-id="ec327-126">C# 버전 2.0부터 단순 형식 또는 열거형 형식에 `sizeof`를 적용하면 [안전하지 않은](unsafe.md) 컨텍스트에서 코드를 더 이상 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="ec327-127">`sizeof` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="ec327-128">`sizeof` 연산자에서 반환되는 값은 `int` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="ec327-129">이전 표에서는 특정 단순 형식이 피연산자로 포함된 `sizeof` 식을 대체하는 상수 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="ec327-130">구조체를 비롯한 다른 모든 형식의 경우 `sizeof` 연산자는 안전하지 않은 코드 블록에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="ec327-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 메서드를 사용할 수 있지만 이 메서드에서 반환된 값이 `sizeof`에서 반환된 값과 항상 같지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="ec327-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>는 형식이 마샬링된 후의 크기를 반환하는 반면, `sizeof`는 안쪽 여백을 포함하여 공용 언어 런타임에 의해 할당된 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec327-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="ec327-133">예제</span><span class="sxs-lookup"><span data-stu-id="ec327-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="ec327-134">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ec327-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ec327-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec327-135">See also</span></span>

- [<span data-ttu-id="ec327-136">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ec327-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ec327-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ec327-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ec327-138">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="ec327-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ec327-139">enum</span><span class="sxs-lookup"><span data-stu-id="ec327-139">enum</span></span>](enum.md)
- [<span data-ttu-id="ec327-140">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="ec327-140">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="ec327-141">구조체</span><span class="sxs-lookup"><span data-stu-id="ec327-141">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="ec327-142">상수</span><span class="sxs-lookup"><span data-stu-id="ec327-142">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)
