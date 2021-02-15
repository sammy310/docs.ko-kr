---
description: '자세히 알아보기: 방법: 변수에 둘 이상의 값 저장 (Visual Basic)'
title: '방법: 변수에 두 개 이상의 값 사용'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 5248bc29f58cccf3b8ced95d3fba8f0d39033a83
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100484004"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="596a4-103">방법: 변수에 두 개 이상의 값 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="596a4-103">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="596a4-104">*복합 데이터 형식* 으로 선언 하는 경우 변수에 두 개 이상의 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-104">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="596a4-105">[복합 데이터 형식](composite-data-types.md) 에는 구조체, 배열 및 클래스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-105">[Composite Data Types](composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="596a4-106">복합 데이터 형식의 변수는 기본 데이터 형식과 기타 복합 형식의 조합을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-106">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="596a4-107">구조체와 클래스는 데이터 뿐만 아니라 코드도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-107">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="596a4-108">변수에 두 개 이상의 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="596a4-108">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="596a4-109">변수에 사용 하려는 복합 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-109">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="596a4-110">복합 데이터 형식이 아직 정의 되지 않은 경우 변수에서 사용할 수 있도록 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-110">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="596a4-111">Structure [문을](../../../language-reference/statements/structure-statement.md)사용 하 여 구조체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-111">Define a structure with a [Structure Statement](../../../language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="596a4-112">[Dim 문으로](../../../language-reference/statements/dim-statement.md)배열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-112">Define an array with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="596a4-113">[클래스 문으로](../../../language-reference/statements/class-statement.md)클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-113">Define a class with a [Class Statement](../../../language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="596a4-114">문을 사용 하 여 변수를 선언 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-114">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="596a4-115">변수 이름 뒤에 절을 추가 `As` 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-115">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="596a4-116">키워드 뒤에 `As` 적절 한 복합 데이터 형식의 이름을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="596a4-116">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="596a4-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="596a4-117">See also</span></span>

- [<span data-ttu-id="596a4-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="596a4-118">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="596a4-119">형식 문자</span><span class="sxs-lookup"><span data-stu-id="596a4-119">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="596a4-120">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="596a4-120">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="596a4-121">구조체</span><span class="sxs-lookup"><span data-stu-id="596a4-121">Structures</span></span>](structures.md)
- [<span data-ttu-id="596a4-122">배열</span><span class="sxs-lookup"><span data-stu-id="596a4-122">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="596a4-123">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="596a4-123">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="596a4-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="596a4-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
