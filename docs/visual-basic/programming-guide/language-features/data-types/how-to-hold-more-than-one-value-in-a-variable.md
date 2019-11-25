---
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
ms.openlocfilehash: d452fbf35f9d200348234b38c40f8636f0ec4b4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350015"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="21d77-102">방법: 변수에 두 개 이상의 값 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21d77-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="21d77-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span><span class="sxs-lookup"><span data-stu-id="21d77-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="21d77-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span><span class="sxs-lookup"><span data-stu-id="21d77-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="21d77-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span><span class="sxs-lookup"><span data-stu-id="21d77-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="21d77-106">Structures and classes can hold code as well as data.</span><span class="sxs-lookup"><span data-stu-id="21d77-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="21d77-107">To hold more than one value in a variable</span><span class="sxs-lookup"><span data-stu-id="21d77-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="21d77-108">Determine what composite data type you want to use for your variable.</span><span class="sxs-lookup"><span data-stu-id="21d77-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="21d77-109">If the composite data type is not already defined, define it so that your variable can use it.</span><span class="sxs-lookup"><span data-stu-id="21d77-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="21d77-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21d77-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="21d77-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21d77-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="21d77-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21d77-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="21d77-113">Declare your variable with a `Dim` statement.</span><span class="sxs-lookup"><span data-stu-id="21d77-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="21d77-114">Follow the variable name with an `As` clause.</span><span class="sxs-lookup"><span data-stu-id="21d77-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="21d77-115">Follow the `As` keyword with the name of the appropriate composite data type.</span><span class="sxs-lookup"><span data-stu-id="21d77-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="21d77-116">참조</span><span class="sxs-lookup"><span data-stu-id="21d77-116">See also</span></span>

- [<span data-ttu-id="21d77-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="21d77-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="21d77-118">형식 문자</span><span class="sxs-lookup"><span data-stu-id="21d77-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="21d77-119">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="21d77-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="21d77-120">구조체</span><span class="sxs-lookup"><span data-stu-id="21d77-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="21d77-121">배열</span><span class="sxs-lookup"><span data-stu-id="21d77-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="21d77-122">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="21d77-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="21d77-123">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="21d77-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
