---
title: '방법: 변수 값 저장 및 검색'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346898"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="a4100-102">방법: 변수 값 저장 및 검색(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4100-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="a4100-103">변수 이름을 대입문의 왼쪽에 배치 하 여 변수에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="a4100-104">변수에 데이터 배치</span><span class="sxs-lookup"><span data-stu-id="a4100-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="a4100-105">변수에 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="a4100-105">To store a value in a variable</span></span>

- <span data-ttu-id="a4100-106">대입문의 왼쪽에 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="a4100-107">다음 예에서는 `alpha`변수의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="a4100-108">대입문의 오른쪽에 생성 된 값은 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="a4100-109">변수에서 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="a4100-109">Getting Data from a Variable</span></span>

<span data-ttu-id="a4100-110">식에 변수 이름을 포함 하 여 변수의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="a4100-111">변수에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="a4100-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="a4100-112">식에서 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-112">Use the variable name in an expression.</span></span> <span data-ttu-id="a4100-113">상수 값을 정의 하는 식을 제외 하 고 상수 또는 리터럴을 사용할 수 있는 모든 위치에서 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="a4100-114">\-또는-</span><span class="sxs-lookup"><span data-stu-id="a4100-114">\-or-</span></span>

- <span data-ttu-id="a4100-115">대입문에서 등호 (`=`) 뒤에 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="a4100-116">다음 예에서는 `startValue` 변수의 값을 읽은 다음 식에 `counter` 변수 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="a4100-117">변수 값은 상수와 마찬가지로 식에도 관여 하 고 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4100-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4100-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4100-118">See also</span></span>

- [<span data-ttu-id="a4100-119">변수</span><span class="sxs-lookup"><span data-stu-id="a4100-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="a4100-120">변수 선언</span><span class="sxs-lookup"><span data-stu-id="a4100-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a4100-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="a4100-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
