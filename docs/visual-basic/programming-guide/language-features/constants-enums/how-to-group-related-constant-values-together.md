---
description: '자세한 정보: 방법: 관련 상수 값 그룹화 (Visual Basic)'
title: '방법: 관련 상수 값 그룹화'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: ddd60696d2c751810e49ecbcb537589bedc58abf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471593"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="486ca-103">방법: 관련 상수 값 그룹화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="486ca-103">How to: Group Related Constant Values Together (Visual Basic)</span></span>

<span data-ttu-id="486ca-104">열거형은 관련 상수를 함께 그룹화 하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="486ca-104">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="486ca-105">`Enum`클래스 또는 모듈의 선언 섹션에 문을 사용 하 여 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="486ca-105">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="486ca-106">자세한 내용은 [방법: 열거형 선언](how-to-declare-enumerations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="486ca-106">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="486ca-107">관련 상수 값을 그룹화 하려면</span><span class="sxs-lookup"><span data-stu-id="486ca-107">To group related constant values</span></span>  
  
1. <span data-ttu-id="486ca-108">코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ca-108">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="486ca-109">이 예제에서는 `Private` 열거형을 만듭니다 `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="486ca-109">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="486ca-110">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ca-110">Define the constants in the enumeration.</span></span> <span data-ttu-id="486ca-111">이 예제에서는 열거형을 만들고 `Public` `temperatureValues` 해당 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="486ca-111">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="486ca-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="486ca-112">See also</span></span>

- [<span data-ttu-id="486ca-113">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="486ca-113">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="486ca-114">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="486ca-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="486ca-115">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="486ca-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="486ca-116">상수 개요</span><span class="sxs-lookup"><span data-stu-id="486ca-116">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="486ca-117">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="486ca-117">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="486ca-118">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="486ca-118">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
