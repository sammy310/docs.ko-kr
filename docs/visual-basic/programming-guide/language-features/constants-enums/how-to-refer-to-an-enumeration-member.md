---
title: '방법: 열거형 멤버 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 01db5b84783eda45cd7867dc8fea8a69fc18b98a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353992"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="f0cdd-102">방법: 열거형 멤버 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0cdd-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="f0cdd-103">열거형은 관련 상수 집합을 사용 하는 편리한 방법을 제공 하 고 상수 값을 이름에 연결 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="f0cdd-104">예를 들어 요일과 연결된 정수 상수에 대한 열거형을 선언한 다음, 코드에 정수 값 대신 요일 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="f0cdd-105">`Imports` 문으로 정규화 된 이름을 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="f0cdd-106">자세한 내용은 [열거 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="f0cdd-107">열거형 멤버를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="f0cdd-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="f0cdd-108">열거형을 사용 하 여 멤버 이름을 한정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="f0cdd-109">예를 들어 다음 예에서는 `FirstDayOfWeek` 열거형의 `Saturday` 멤버를 `DayValue`변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="f0cdd-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0cdd-110">See also</span></span>

- [<span data-ttu-id="f0cdd-111">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="f0cdd-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="f0cdd-112">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="f0cdd-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="f0cdd-113">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="f0cdd-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="f0cdd-114">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="f0cdd-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="f0cdd-115">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="f0cdd-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
