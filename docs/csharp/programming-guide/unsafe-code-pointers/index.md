---
title: 안전하지 않은 코드 및 포인터 - C# 프로그래밍 가이드
description: 안전하지 않은 코드 및 포인터에 대해 알아봅니다. C#에서는 포인터를 지원하지 않지만 ‘unsafe’ 키워드와 함께 포인터를 사용할 수 있는 안전하지 않은 컨텍스트를 정의할 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 4d624bdc8fc4a756f47d66c9dec6eba8c24a9d9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782392"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="4b6f8-104">안전하지 않은 코드 및 포인터 - (C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4b6f8-104">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="4b6f8-105">형식 안전성 및 보안을 유지하기 위해 C#에서는 포인터 산술 연산을 기본적으로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-105">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="4b6f8-106">그러나 [unsafe](../../language-reference/keywords/unsafe.md) 키워드를 사용하여 포인터를 사용할 수 있는 안전하지 않은 컨텍스트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-106">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="4b6f8-107">포인터에 대한 자세한 내용은 [포인터 형식](pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-107">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b6f8-108">CLR(공용 언어 런타임)에서 안전하지 않은 코드를 확인할 수 없는 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-108">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="4b6f8-109">C#에 안전하지 않은 코드가 반드시 위험한 것은 아니며, CLR에서 안전을 확인할 수 없는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-109">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="4b6f8-110">그러므로 CLR은 완전히 신뢰할 수 있는 어셈블리에 있는 경우 안전하지 않은 코드만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-110">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="4b6f8-111">안전하지 않은 코드를 사용하는 경우 코드로 인해 보안 위험이나 포인터 오류가 발생하지 않도록 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-111">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="4b6f8-112">안전하지 않은 코드 개요</span><span class="sxs-lookup"><span data-stu-id="4b6f8-112">Unsafe code overview</span></span>

<span data-ttu-id="4b6f8-113">안전하지 않은 코드에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-113">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="4b6f8-114">메서드, 형식 및 코드 블록은 안전하지 않은 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-114">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="4b6f8-115">경우에 따라 안전하지 않은 코드는 배열 범위 검사를 제거하여 애플리케이션의 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-115">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="4b6f8-116">포인터가 필요한 네이티브 함수를 호출하는 경우 안전하지 않은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-116">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="4b6f8-117">안전하지 않은 코드를 사용하면 보안 및 안정성 위험이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-117">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="4b6f8-118">안전하지 않은 블록을 포함하는 코드는 [-안전하지 않은](../../language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션을 사용하여 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-118">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="4b6f8-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4b6f8-119">Related sections</span></span>

<span data-ttu-id="4b6f8-120">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-120">For more information, see:</span></span>

- [<span data-ttu-id="4b6f8-121">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="4b6f8-121">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="4b6f8-122">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="4b6f8-122">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="4b6f8-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4b6f8-123">C# language specification</span></span>

<span data-ttu-id="4b6f8-124">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [안전하지 않은 코드](~/_csharplang/spec/unsafe-code.md) 토픽을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b6f8-124">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b6f8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b6f8-125">See also</span></span>

- [<span data-ttu-id="4b6f8-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4b6f8-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4b6f8-127">unsafe</span><span class="sxs-lookup"><span data-stu-id="4b6f8-127">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
