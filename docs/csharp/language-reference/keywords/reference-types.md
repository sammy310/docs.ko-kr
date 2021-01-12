---
description: 참조 형식 - C# 참조
title: 참조 형식 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 075ec5ecd8f71f5cb85bab0e2baff56409709191
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899615"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="f56f2-103">참조 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f56f2-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="f56f2-104">C# 형식은 참조 형식과 값 형식 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f56f2-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="f56f2-105">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f56f2-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="f56f2-106">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f56f2-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="f56f2-107">값 형식에서는 각 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(in, ref 및 out 매개 변수 제외, [in](in-parameter-modifier.md), [ref](ref.md) 및 [out](out-parameter-modifier.md) 매개 변수 한정자 참조).</span><span class="sxs-lookup"><span data-stu-id="f56f2-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="f56f2-108">다음 키워드는 참조 형식을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f56f2-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="f56f2-109">class</span><span class="sxs-lookup"><span data-stu-id="f56f2-109">class</span></span>](class.md)

- [<span data-ttu-id="f56f2-110">interface</span><span class="sxs-lookup"><span data-stu-id="f56f2-110">interface</span></span>](interface.md)

- [<span data-ttu-id="f56f2-111">delegate</span><span class="sxs-lookup"><span data-stu-id="f56f2-111">delegate</span></span>](../builtin-types/reference-types.md)
- [<span data-ttu-id="f56f2-112">record</span><span class="sxs-lookup"><span data-stu-id="f56f2-112">record</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="f56f2-113">C#는 다음과 같은 기본 참조 형식도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f56f2-113">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="f56f2-114">dynamic</span><span class="sxs-lookup"><span data-stu-id="f56f2-114">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="f56f2-115">object</span><span class="sxs-lookup"><span data-stu-id="f56f2-115">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="f56f2-116">string</span><span class="sxs-lookup"><span data-stu-id="f56f2-116">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="f56f2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f56f2-117">See also</span></span>

- [<span data-ttu-id="f56f2-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f56f2-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f56f2-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f56f2-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f56f2-120">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="f56f2-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="f56f2-121">값 형식</span><span class="sxs-lookup"><span data-stu-id="f56f2-121">Value types</span></span>](../builtin-types/value-types.md)
