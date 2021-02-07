---
description: '자세한 정보: BC36564: 형식 인수를 대리자에서 유추할 수 없습니다.'
title: 대리자에서 형식 인수를 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1a83ee64df4523cee87d0d677ddafaeadfe5543d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666266"
---
# <a name="bc36564-type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="98d48-103">BC36564: 대리자에서 형식 인수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-103">BC36564: Type arguments could not be inferred from the delegate</span></span>

<span data-ttu-id="98d48-104">대입문이 `AddressOf` 를 사용하여 제네릭 프로시저의 주소를 대리자에게 할당하지만 형식 인수를 제네릭 프로시저에 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-104">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>

 <span data-ttu-id="98d48-105">일반적으로 제네릭 형식을 호출하는 경우 제네릭 형식이 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-105">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="98d48-106">형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-106">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="98d48-107">컨텍스트에서 컴파일러가 형식을 유추하도록 정보를 충분히 제공하지 않으면 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-107">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>

 <span data-ttu-id="98d48-108">**오류 ID:** BC36564</span><span class="sxs-lookup"><span data-stu-id="98d48-108">**Error ID:** BC36564</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="98d48-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="98d48-109">To correct this error</span></span>

- <span data-ttu-id="98d48-110">`AddressOf` 식에서 제네릭 프로시저에 대한 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98d48-110">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>

## <a name="see-also"></a><span data-ttu-id="98d48-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98d48-111">See also</span></span>

- [<span data-ttu-id="98d48-112">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="98d48-112">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="98d48-113">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="98d48-113">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="98d48-114">Visual Basic의 제네릭 프로시저</span><span class="sxs-lookup"><span data-stu-id="98d48-114">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="98d48-115">Type List</span><span class="sxs-lookup"><span data-stu-id="98d48-115">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="98d48-116">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="98d48-116">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
