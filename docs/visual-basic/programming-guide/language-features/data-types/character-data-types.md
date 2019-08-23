---
title: 문자 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965686"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="bf717-102">문자 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf717-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="bf717-103">Visual Basic은 인쇄 가능 하 고 표시할 수 있는 문자를 처리 하는 *문자 데이터 형식을* 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="bf717-104">두 가지 모두 유니코드 문자를 처리 하 `Char` 는 반면에는 단일 `String` 문자를 포함 하 고는 무한 문자 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="bf717-105">Visual Basic 데이터 형식에 대 한 병렬 비교를 표시 하는 표는 [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf717-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="bf717-106">Char 형식</span><span class="sxs-lookup"><span data-stu-id="bf717-106">Char Type</span></span>  
 <span data-ttu-id="bf717-107">`Char` 데이터 형식은 단일 2 바이트 (16 비트) 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="bf717-108">변수가 항상 정확히 하나의 문자를 저장 하는 경우로 `Char`선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="bf717-109">예:</span><span class="sxs-lookup"><span data-stu-id="bf717-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="bf717-110">`Char` 또는`String` 변수에서 사용할 수 있는 각 값은 유니코드 문자 집합의 *코드 포인트*또는 문자 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="bf717-111">유니코드 문자에는 기본 ASCII 문자 집합, 다양 한 영문자, 악센트, 통화 기호, 분수, 분음 부호, 수학 및 기술 기호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf717-112">유니코드 문자 집합은 단일 코드 포인트를 나타내는 2 16 비트 값이 필요한 *서로게이트 쌍*에 대해 d 800 (55296 ~ 55551 decimal)까지 코드 포인트를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="bf717-113">변수 `Char` 는 서로게이트 쌍을 포함할 수 없으며,는 `String` 두 개의 위치를 사용 하 여 이러한 쌍을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="bf717-114">자세한 내용은 [Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf717-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="bf717-115">문자열 형식</span><span class="sxs-lookup"><span data-stu-id="bf717-115">String Type</span></span>  
 <span data-ttu-id="bf717-116">`String` 데이터 형식은 0 개 이상의 2 바이트 (16 비트) 유니코드 문자 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="bf717-117">변수에 무한 수의 문자가 포함 될 수 있는 경우로 `String`선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf717-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="bf717-118">예:</span><span class="sxs-lookup"><span data-stu-id="bf717-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="bf717-119">자세한 내용은 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf717-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf717-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf717-120">See also</span></span>

- [<span data-ttu-id="bf717-121">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf717-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="bf717-122">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bf717-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="bf717-123">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="bf717-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="bf717-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="bf717-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="bf717-125">Visual Basic 형식 변환</span><span class="sxs-lookup"><span data-stu-id="bf717-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bf717-126">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bf717-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="bf717-127">형식 문자</span><span class="sxs-lookup"><span data-stu-id="bf717-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
