---
title: AddressOf 연산자
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: edce7d4a2268bd311045ea4972672fe8fd2600ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874892"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="76635-102">AddressOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76635-102">AddressOf Operator (Visual Basic)</span></span>

<span data-ttu-id="76635-103">특정 프로시저를 참조 하는 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76635-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76635-104">구문</span><span class="sxs-lookup"><span data-stu-id="76635-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="76635-105">부분</span><span class="sxs-lookup"><span data-stu-id="76635-105">Parts</span></span>  

 `procedurename`  
 <span data-ttu-id="76635-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="76635-106">Required.</span></span> <span data-ttu-id="76635-107">새로 만든 대리자가 참조 하는 프로시저를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76635-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76635-108">설명</span><span class="sxs-lookup"><span data-stu-id="76635-108">Remarks</span></span>  

 <span data-ttu-id="76635-109">연산자는에 `AddressOf` 지정 된 sub 또는 함수를 가리키는 대리자를 만듭니다 `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="76635-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="76635-110">지정 된 프로시저가 인스턴스 메서드인 경우 대리자는 인스턴스와 메서드를 모두 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="76635-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="76635-111">그런 다음 대리자가 호출 되 면 지정 된 인스턴스의 지정 된 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76635-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="76635-112">`AddressOf`연산자는 대리자 생성자의 피연산자로 사용 하거나 대리자의 형식을 컴파일러에서 확인할 수 있는 컨텍스트에서 사용할 수 있습니다 (예를 들어,</span><span class="sxs-lookup"><span data-stu-id="76635-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76635-113">예제</span><span class="sxs-lookup"><span data-stu-id="76635-113">Example</span></span>  

 <span data-ttu-id="76635-114">이 예제에서는 연산자를 사용 하 여 `AddressOf` 단추의 이벤트를 처리할 대리자를 지정 `Click` 합니다.</span><span class="sxs-lookup"><span data-stu-id="76635-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="76635-115">예제</span><span class="sxs-lookup"><span data-stu-id="76635-115">Example</span></span>  

 <span data-ttu-id="76635-116">다음 예에서는 연산자를 사용 하 여 `AddressOf` 스레드에 대 한 시작 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76635-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="76635-117">참조</span><span class="sxs-lookup"><span data-stu-id="76635-117">See also</span></span>

- [<span data-ttu-id="76635-118">Declare 문</span><span class="sxs-lookup"><span data-stu-id="76635-118">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="76635-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="76635-119">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="76635-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="76635-120">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="76635-121">대리자</span><span class="sxs-lookup"><span data-stu-id="76635-121">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
