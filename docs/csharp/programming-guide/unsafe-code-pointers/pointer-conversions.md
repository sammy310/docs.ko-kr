---
title: 포인터 변환 - C# 프로그래밍 가이드
description: 포인터 변환에 대해 알아봅니다. 암시적 및 명시적 포인터 변환 표, 코드 예제 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: c39be5cb52964abbea5bc5636c6fa74d8411a331
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382089"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="10a0b-104">포인터 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="10a0b-104">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="10a0b-105">다음 표에서는 미리 정의된 암시적 포인터 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="10a0b-106">암시적 변환은 메서드 호출, 할당 문을 비롯한 대부분의 경우에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="10a0b-107">암시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="10a0b-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="10a0b-108">시작</span><span class="sxs-lookup"><span data-stu-id="10a0b-108">From</span></span>|<span data-ttu-id="10a0b-109">대상</span><span class="sxs-lookup"><span data-stu-id="10a0b-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="10a0b-110">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-110">Any pointer type</span></span>|<span data-ttu-id="10a0b-111">void\*</span><span class="sxs-lookup"><span data-stu-id="10a0b-111">void\*</span></span>|  
|<span data-ttu-id="10a0b-112">null</span><span class="sxs-lookup"><span data-stu-id="10a0b-112">null</span></span>|<span data-ttu-id="10a0b-113">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="10a0b-114">명시적 포인터 변환은 캐스트 식을 통해 암시적 변환이 없는 변환을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="10a0b-115">다음 표에는 이러한 변환이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="10a0b-116">명시적 포인터 변환</span><span class="sxs-lookup"><span data-stu-id="10a0b-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="10a0b-117">시작</span><span class="sxs-lookup"><span data-stu-id="10a0b-117">From</span></span>|<span data-ttu-id="10a0b-118">대상</span><span class="sxs-lookup"><span data-stu-id="10a0b-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="10a0b-119">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-119">Any pointer type</span></span>|<span data-ttu-id="10a0b-120">다른 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-120">Any other pointer type</span></span>|  
|<span data-ttu-id="10a0b-121">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="10a0b-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="10a0b-122">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-122">Any pointer type</span></span>|  
|<span data-ttu-id="10a0b-123">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-123">Any pointer type</span></span>|<span data-ttu-id="10a0b-124">sbyte, byte, short, ushort, int, uint, long 또는 ulong</span><span class="sxs-lookup"><span data-stu-id="10a0b-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10a0b-125">예제</span><span class="sxs-lookup"><span data-stu-id="10a0b-125">Example</span></span>  
 <span data-ttu-id="10a0b-126">다음 예제에서 `int`에 대한 포인터는 `byte`에 대한 포인터로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="10a0b-127">포인터는 변수의 최하위 주소 지정 바이트를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="10a0b-128">`int` 크기(4바이트)까지 결과를 연속적으로 증가할 경우 변수의 나머지 바이트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a0b-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="10a0b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10a0b-129">See also</span></span>

- [<span data-ttu-id="10a0b-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="10a0b-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="10a0b-131">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="10a0b-132">참조 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="10a0b-133">값 형식</span><span class="sxs-lookup"><span data-stu-id="10a0b-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="10a0b-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="10a0b-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="10a0b-135">fixed 문</span><span class="sxs-lookup"><span data-stu-id="10a0b-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="10a0b-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="10a0b-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
