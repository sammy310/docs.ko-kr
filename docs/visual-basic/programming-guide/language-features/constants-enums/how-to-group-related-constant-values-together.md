---
title: '방법: 그룹 관련된 상수 값 그룹화 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 9174bcd2385103cf7fa1daf3133e388f9b4998a4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843763"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="b3866-102">방법: 그룹 관련된 상수 값 그룹화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3866-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="b3866-103">열거형은 가장 좋은 방법은 관련된 상수를 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="b3866-104">사용 하 여 열거형을 만듭니다는 `Enum` 클래스 또는 모듈의 선언 섹션에서 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="b3866-105">자세한 내용은 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="b3866-106">그룹에 관련 상수 값</span><span class="sxs-lookup"><span data-stu-id="b3866-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="b3866-107">코드 액세스 수준에 포함 하는 선언을 작성 합니다 `Enum` 키워드 및 유효한 이름이입니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="b3866-108">이 예제에서는 합니다 `Private` 열거형 `temperatureValues`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  <span data-ttu-id="b3866-109">열거형의 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="b3866-110">이 예제에서는 합니다 `Public` 열거형 `temperatureValues` 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3866-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b3866-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3866-111">See also</span></span>

- [<span data-ttu-id="b3866-112">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="b3866-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="b3866-113">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="b3866-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="b3866-114">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="b3866-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="b3866-115">상수 개요</span><span class="sxs-lookup"><span data-stu-id="b3866-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="b3866-116">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3866-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="b3866-117">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="b3866-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
