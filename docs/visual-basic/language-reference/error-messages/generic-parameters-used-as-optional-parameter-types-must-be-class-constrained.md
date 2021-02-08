---
description: '자세한 내용은 다음에 대해 자세히 알아보세요. BC32124: 선택적 매개 변수 형식으로 사용 되는 제네릭 매개 변수는 클래스 제한 이어야 합니다.'
title: 선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 0014720d55dc4395178186b5e183d5b0279d7029
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796147"
---
# <a name="bc32124-generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="4202d-103">BC32124: 선택적 매개 변수 형식으로 사용 되는 제네릭 매개 변수는 클래스 제약 조건 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-103">BC32124: Generic parameters used as optional parameter types must be class constrained</span></span>

<span data-ttu-id="4202d-104">프로시저는 참조 형식으로 제한 되지 않는 형식 매개 변수를 사용 하는 선택적 매개 변수를 사용 하 여 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-104">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>

 <span data-ttu-id="4202d-105">항상 각 선택적 매개 변수에 대 한 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-105">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="4202d-106">매개 변수가 참조 형식이 면 선택적 값은 `Nothing` 모든 참조 형식에 유효한 값인로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-106">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="4202d-107">그러나 매개 변수가 값 형식이 면 해당 형식은 Visual Basic에 의해 미리 정의 된 기본 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-107">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="4202d-108">이는 사용자 정의 구조체와 같은 복합 값 형식에 유효한 기본값이 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-108">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>

 <span data-ttu-id="4202d-109">선택적 매개 변수에 대 한 형식 매개 변수를 사용 하는 경우 유효한 기본값이 없는 값 형식의 가능성을 방지 하기 위해 해당 매개 변수를 참조 형식으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-109">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="4202d-110">즉 `Class` , 키워드를 사용 하거나 특정 클래스의 이름을 사용 하 여 형식 매개 변수를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-110">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>

 <span data-ttu-id="4202d-111">**오류 ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="4202d-111">**Error ID:** BC32124</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4202d-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4202d-112">To correct this error</span></span>

- <span data-ttu-id="4202d-113">참조 형식만 허용 하도록 형식 매개 변수를 제한 하거나 선택적 매개 변수에 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4202d-113">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="4202d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4202d-114">See also</span></span>

- [<span data-ttu-id="4202d-115">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="4202d-115">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="4202d-116">Type List</span><span class="sxs-lookup"><span data-stu-id="4202d-116">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="4202d-117">Class 문</span><span class="sxs-lookup"><span data-stu-id="4202d-117">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="4202d-118">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4202d-118">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="4202d-119">구조체</span><span class="sxs-lookup"><span data-stu-id="4202d-119">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4202d-120">Nothing</span><span class="sxs-lookup"><span data-stu-id="4202d-120">Nothing</span></span>](../nothing.md)
