---
title: '방법: 변수에 둘 이상의 값 (Visual Basic)'
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
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332263"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="71530-102">방법: 변수에 둘 이상의 값 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71530-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="71530-103">변수를 선언 하면 둘 이상의 값을 보유 한 *복합 데이터 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="71530-104">[복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) 구조, 배열 및 클래스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="71530-105">복합 데이터 형식 변수의 기본 데이터 형식 및 다른 복합 형식의 조합을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71530-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="71530-106">구조체 및 클래스 코드 뿐만 아니라 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71530-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="71530-107">변수에 둘 이상의 값을 보유할</span><span class="sxs-lookup"><span data-stu-id="71530-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="71530-108">변수에 대 한 사용 하려면 복합 데이터 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="71530-109">복합 데이터 형식이 이미 정의 되어 있지 않으면 정의 변수에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="71530-110">정의 하는 구조체를 [Structure 문을](../../../../visual-basic/language-reference/statements/structure-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="71530-111">배열을 사용 하 여 정의 된 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="71530-112">클래스 정의 [Class 문](../../../../visual-basic/language-reference/statements/class-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="71530-113">사용 하 여 변수를 선언 된 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="71530-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="71530-114">변수 이름 뒤에 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="71530-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="71530-115">수행 된 `As` 키워드와 적절 한 복합 데이터 형식의 이름 합니다.</span><span class="sxs-lookup"><span data-stu-id="71530-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71530-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="71530-116">See also</span></span>

- [<span data-ttu-id="71530-117">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="71530-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="71530-118">형식 문자</span><span class="sxs-lookup"><span data-stu-id="71530-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="71530-119">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="71530-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="71530-120">구조체</span><span class="sxs-lookup"><span data-stu-id="71530-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="71530-121">배열</span><span class="sxs-lookup"><span data-stu-id="71530-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="71530-122">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="71530-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="71530-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="71530-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
