---
title: 참조 형식 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 16e7cdc624979f9a35e287ea5274bd9398c83132
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715171"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="21590-102">참조 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="21590-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="21590-103">C# 형식은 참조 형식과 값 형식 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21590-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="21590-104">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21590-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="21590-105">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21590-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="21590-106">값 형식에서는 각 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(in, ref 및 out 매개 변수 제외, [in](in-parameter-modifier.md), [ref](ref.md) 및 [out](out-parameter-modifier.md) 매개 변수 한정자 참조).</span><span class="sxs-lookup"><span data-stu-id="21590-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="21590-107">다음 키워드는 참조 형식을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21590-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="21590-108">class</span><span class="sxs-lookup"><span data-stu-id="21590-108">class</span></span>](class.md)

- [<span data-ttu-id="21590-109">interface</span><span class="sxs-lookup"><span data-stu-id="21590-109">interface</span></span>](interface.md)

- [<span data-ttu-id="21590-110">delegate</span><span class="sxs-lookup"><span data-stu-id="21590-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="21590-111">C#는 다음과 같은 기본 참조 형식도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21590-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="21590-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="21590-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="21590-113">object</span><span class="sxs-lookup"><span data-stu-id="21590-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="21590-114">string</span><span class="sxs-lookup"><span data-stu-id="21590-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="21590-115">참조</span><span class="sxs-lookup"><span data-stu-id="21590-115">See also</span></span>

- [<span data-ttu-id="21590-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="21590-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21590-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="21590-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21590-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="21590-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="21590-119">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="21590-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="21590-120">값 형식</span><span class="sxs-lookup"><span data-stu-id="21590-120">Value types</span></span>](value-types.md)
