---
description: '자세한 정보: AddressOf 연산자 (Visual Basic)'
title: AddressOf 연산자
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2aba8c26aa9581fe1070574b8c408e09bf063d1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774384"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="ffc0e-103">AddressOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffc0e-103">AddressOf Operator (Visual Basic)</span></span>

<span data-ttu-id="ffc0e-104">특정 프로시저를 참조 하는 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-104">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc0e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffc0e-105">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="ffc0e-106">부분</span><span class="sxs-lookup"><span data-stu-id="ffc0e-106">Parts</span></span>  

 `procedurename`  
 <span data-ttu-id="ffc0e-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-107">Required.</span></span> <span data-ttu-id="ffc0e-108">새로 만든 대리자가 참조 하는 프로시저를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-108">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffc0e-109">설명</span><span class="sxs-lookup"><span data-stu-id="ffc0e-109">Remarks</span></span>  

 <span data-ttu-id="ffc0e-110">연산자는에 `AddressOf` 지정 된 sub 또는 함수를 가리키는 대리자를 만듭니다 `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="ffc0e-110">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="ffc0e-111">지정 된 프로시저가 인스턴스 메서드인 경우 대리자는 인스턴스와 메서드를 모두 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-111">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="ffc0e-112">그런 다음 대리자가 호출 되 면 지정 된 인스턴스의 지정 된 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-112">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="ffc0e-113">`AddressOf`연산자는 대리자 생성자의 피연산자로 사용 하거나 대리자의 형식을 컴파일러에서 확인할 수 있는 컨텍스트에서 사용할 수 있습니다 (예를 들어,</span><span class="sxs-lookup"><span data-stu-id="ffc0e-113">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffc0e-114">예제</span><span class="sxs-lookup"><span data-stu-id="ffc0e-114">Example</span></span>  

 <span data-ttu-id="ffc0e-115">이 예제에서는 연산자를 사용 하 여 `AddressOf` 단추의 이벤트를 처리할 대리자를 지정 `Click` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-115">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="ffc0e-116">예제</span><span class="sxs-lookup"><span data-stu-id="ffc0e-116">Example</span></span>  

 <span data-ttu-id="ffc0e-117">다음 예에서는 연산자를 사용 하 여 `AddressOf` 스레드에 대 한 시작 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0e-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="ffc0e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffc0e-118">See also</span></span>

- [<span data-ttu-id="ffc0e-119">Declare 문</span><span class="sxs-lookup"><span data-stu-id="ffc0e-119">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="ffc0e-120">Function 문</span><span class="sxs-lookup"><span data-stu-id="ffc0e-120">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="ffc0e-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ffc0e-121">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="ffc0e-122">대리자</span><span class="sxs-lookup"><span data-stu-id="ffc0e-122">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
