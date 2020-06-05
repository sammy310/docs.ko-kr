---
title: '방법: 변수 값 저장 및 검색'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: fe19a6160623aa9ea867becdf7a15b51319abf45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410440"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="850c1-102">방법: 변수 값 저장 및 검색(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="850c1-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="850c1-103">변수 이름을 대입문의 왼쪽에 배치 하 여 변수에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="850c1-104">변수에 데이터 배치</span><span class="sxs-lookup"><span data-stu-id="850c1-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="850c1-105">변수에 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="850c1-105">To store a value in a variable</span></span>

- <span data-ttu-id="850c1-106">대입문의 왼쪽에 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="850c1-107">다음 예에서는 변수의 값을 설정 합니다 `alpha` .</span><span class="sxs-lookup"><span data-stu-id="850c1-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="850c1-108">대입문의 오른쪽에 생성 된 값은 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="850c1-109">변수에서 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="850c1-109">Getting Data from a Variable</span></span>

<span data-ttu-id="850c1-110">식에 변수 이름을 포함 하 여 변수의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="850c1-111">변수에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="850c1-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="850c1-112">식에서 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-112">Use the variable name in an expression.</span></span> <span data-ttu-id="850c1-113">상수 값을 정의 하는 식을 제외 하 고 상수 또는 리터럴을 사용할 수 있는 모든 위치에서 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="850c1-114">\-또는-</span><span class="sxs-lookup"><span data-stu-id="850c1-114">\-or-</span></span>

- <span data-ttu-id="850c1-115">대입문에서 등호 () 뒤에 변수 이름을 사용 `=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="850c1-116">다음 예에서는 변수의 값을 읽은 `startValue` 다음 식의 변수 값을 사용 합니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="850c1-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="850c1-117">변수 값은 상수와 마찬가지로 식에도 관여 하 고 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="850c1-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="850c1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="850c1-118">See also</span></span>

- [<span data-ttu-id="850c1-119">변수</span><span class="sxs-lookup"><span data-stu-id="850c1-119">Variables</span></span>](index.md)
- [<span data-ttu-id="850c1-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="850c1-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="850c1-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="850c1-121">Object Variables</span></span>](object-variables.md)
