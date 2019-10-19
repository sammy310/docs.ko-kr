---
title: 문자열과 다른 형식 사이의 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: e1530c1772808249546b453294fc848c31c1e581
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582934"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="d81c1-102">문자열과 다른 형식 사이의 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d81c1-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="d81c1-103">숫자, `Boolean` 또는 날짜/시간 값을 `String`로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="d81c1-104">문자열의 내용이 대상 데이터 형식의 유효한 값으로 해석 될 수 있는 경우 문자열 값에서 숫자, `Boolean` 또는 `Date`으로 반대 방향으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="d81c1-105">사용할 수 없는 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="d81c1-106">어느 방향에서 든 이러한 모든 할당에 대 한 변환은 축소 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="d81c1-107">형식 변환 키워드 (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, 0, 1를 사용 해야 2 , 3 및 4).</span><span class="sxs-lookup"><span data-stu-id="d81c1-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="d81c1-108">@No__t_0 및 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 함수를 통해 문자열과 숫자 간의 변환을 추가로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="d81c1-109">클래스 또는 구조체를 정의한 경우 `String`와 클래스 또는 구조체의 형식 간에 형식 변환 연산자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="d81c1-110">자세한 내용은 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d81c1-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="d81c1-111">숫자를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="d81c1-112">@No__t_0 함수를 사용 하 여 숫자를 서식이 지정 된 문자열로 변환할 수 있습니다. 여기에는 적절 한 숫자 뿐만 아니라 통화 기호 (예: `$`), 천 단위 구분 기호 또는 *자릿수 구분 기호* (예: @no)와 같은 기호 서식 지정도 포함 될 수 있습니다. __t_3) 및 소수 구분 기호 (예: `.`).</span><span class="sxs-lookup"><span data-stu-id="d81c1-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="d81c1-113">`Format`은 Windows **제어판**에 지정 된 **국가별 옵션** 설정에 따라 적절 한 기호를 자동으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="d81c1-114">다음 예제에 나와 있는 것 처럼 연결 (`&`) 연산자는 숫자를 문자열로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="d81c1-115">문자열을 숫자로 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="d81c1-116">@No__t_0 함수를 사용 하 여 문자열의 숫자를 숫자로 명시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="d81c1-117">`Val` 숫자, 공백, 탭, 줄 바꿈 또는 마침표 이외의 문자를 발견할 때까지 문자열을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="d81c1-118">"& O" 및 "& H" 시퀀스는 번호 시스템의 밑수를 변경 하 고 검색을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="d81c1-119">읽기를 중지할 때까지 `Val`는 모든 적절 한 문자를 숫자 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="d81c1-120">예를 들어 다음 문은 `141.825` 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="d81c1-121">Visual Basic 문자열을 숫자 값으로 변환 하는 경우 Windows **제어판** 에 지정 된 **국가별 옵션** 설정을 사용 하 여 천 단위 구분 기호, 소수 구분 기호 및 통화 기호를 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="d81c1-122">즉, 한 설정에서는 변환이 성공 하지만 다른 설정에는 성공 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="d81c1-123">예를 들어 `"$14.20"`은 영어 (미국) 로캘에서는 허용 되지만 프랑스어 로캘에서는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d81c1-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81c1-124">참조</span><span class="sxs-lookup"><span data-stu-id="d81c1-124">See also</span></span>

- [<span data-ttu-id="d81c1-125">Visual Basic 형식 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="d81c1-126">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="d81c1-127">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="d81c1-128">방법: Visual Basic에서 개체를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d81c1-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="d81c1-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="d81c1-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="d81c1-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d81c1-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d81c1-131">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="d81c1-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d81c1-132">.NET Framework 기반의 국가별 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="d81c1-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
