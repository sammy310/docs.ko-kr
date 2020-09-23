---
title: '방법: 관련 상수 값 그룹화'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 0f694aee722e8ce31f663ec9fe52a09a2eb2a958
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058731"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="ce73a-102">방법: 관련 상수 값 그룹화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce73a-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>

<span data-ttu-id="ce73a-103">열거형은 관련 상수를 함께 그룹화 하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ce73a-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="ce73a-104">`Enum`클래스 또는 모듈의 선언 섹션에 문을 사용 하 여 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce73a-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="ce73a-105">자세한 내용은 [방법: 열거형 선언](how-to-declare-enumerations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce73a-105">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="ce73a-106">관련 상수 값을 그룹화 하려면</span><span class="sxs-lookup"><span data-stu-id="ce73a-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="ce73a-107">코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce73a-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="ce73a-108">이 예제에서는 `Private` 열거형을 만듭니다 `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="ce73a-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="ce73a-109">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce73a-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="ce73a-110">이 예제에서는 열거형을 만들고 `Public` `temperatureValues` 해당 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce73a-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ce73a-111">참조</span><span class="sxs-lookup"><span data-stu-id="ce73a-111">See also</span></span>

- [<span data-ttu-id="ce73a-112">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="ce73a-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="ce73a-113">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="ce73a-113">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ce73a-114">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="ce73a-114">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="ce73a-115">상수 개요</span><span class="sxs-lookup"><span data-stu-id="ce73a-115">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="ce73a-116">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ce73a-116">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="ce73a-117">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="ce73a-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
