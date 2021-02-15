---
description: '자세한 정보: 방법: 열거형 멤버 참조 (Visual Basic)'
title: '방법: 열거형 멤버 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 339ea8292eea1b39e2c6e5879b98a083800fb1fc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471528"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="38a9a-103">방법: 열거형 멤버 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38a9a-103">How to: Refer to an Enumeration Member (Visual Basic)</span></span>

<span data-ttu-id="38a9a-104">열거형은 관련 상수 집합을 사용 하는 편리한 방법을 제공 하 고 상수 값을 이름에 연결 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a9a-104">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="38a9a-105">예를 들어 요일과 연결된 정수 상수에 대한 열거형을 선언한 다음, 코드에 정수 값 대신 요일 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a9a-105">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="38a9a-106">문에 정규화 된 이름을 사용 하지 않을 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="38a9a-106">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="38a9a-107">자세한 내용은 [열거 및 이름 한정](enumerations-and-name-qualification.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a9a-107">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="38a9a-108">열거형 멤버를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="38a9a-108">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="38a9a-109">열거형을 사용 하 여 멤버 이름을 한정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a9a-109">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="38a9a-110">예를 들어 다음 예제에서는 `Saturday` 열거형의 멤버를 `FirstDayOfWeek` 변수에 할당 `DayValue` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a9a-110">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="38a9a-111">추가 정보</span><span class="sxs-lookup"><span data-stu-id="38a9a-111">See also</span></span>

- [<span data-ttu-id="38a9a-112">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="38a9a-112">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="38a9a-113">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="38a9a-113">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="38a9a-114">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="38a9a-114">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="38a9a-115">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="38a9a-115">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="38a9a-116">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="38a9a-116">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
