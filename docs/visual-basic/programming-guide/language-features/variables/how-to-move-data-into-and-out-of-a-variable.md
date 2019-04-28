---
title: '방법: 및 변수 (Visual Basic) 외부로 데이터 이동'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756600"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="53791-102">방법: 및 변수 (Visual Basic) 외부로 데이터 이동</span><span class="sxs-lookup"><span data-stu-id="53791-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="53791-103">대입문의 왼쪽에 변수 이름을 입력 하 여 변수에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="53791-104">변수에 데이터를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="53791-105">변수에 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="53791-105">To store a value in a variable</span></span>  
  
- <span data-ttu-id="53791-106">대입문의 왼쪽에 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="53791-107">변수의 값을 설정 하는 다음 예제에서는 `alpha`합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="53791-108">대입문의 오른쪽에 생성 된 값을 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53791-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="53791-109">변수에서 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="53791-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="53791-110">식에서 변수 이름을 포함 하 여 변수의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="53791-111">변수에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="53791-111">To retrieve a value from a variable</span></span>  
  
- <span data-ttu-id="53791-112">식에서 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-112">Use the variable name in an expression.</span></span> <span data-ttu-id="53791-113">변수를 사용할 수 있습니다 어디에서 사용할 수 있습니다 상수 또는 리터럴, 제외 하 고 상수 값을 정의 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="53791-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="53791-114">또는</span><span class="sxs-lookup"><span data-stu-id="53791-114">-or-</span></span>  
  
- <span data-ttu-id="53791-115">등호 다음 변수 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="53791-116">다음 예에서는 변수 값을 읽고 `startValue` 다음 변수의 값을 사용 하 여 `counter` 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53791-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="53791-117">변수의 값은 상수 및 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다 처럼 식에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="53791-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53791-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="53791-118">See also</span></span>

- [<span data-ttu-id="53791-119">변수</span><span class="sxs-lookup"><span data-stu-id="53791-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="53791-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="53791-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="53791-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="53791-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
