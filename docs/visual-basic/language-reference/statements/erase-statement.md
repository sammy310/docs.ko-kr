---
title: Erase 문
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 31aeaf822bc9c1de59a5c5f68406c6521216ae0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404721"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="83a57-102">Erase 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83a57-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="83a57-103">배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리의 할당을 취소 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a57-104">구문</span><span class="sxs-lookup"><span data-stu-id="83a57-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="83a57-105">부분</span><span class="sxs-lookup"><span data-stu-id="83a57-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="83a57-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="83a57-106">Required.</span></span> <span data-ttu-id="83a57-107">지울 배열 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-107">List of array variables to be erased.</span></span> <span data-ttu-id="83a57-108">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a57-109">설명</span><span class="sxs-lookup"><span data-stu-id="83a57-109">Remarks</span></span>  
 <span data-ttu-id="83a57-110">`Erase`문은 프로시저 수준 에서만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="83a57-111">즉, 프로시저 내에서 배열을 해제할 수 있지만 클래스 또는 모듈 수준에서는 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="83a57-112">`Erase`문은 각 배열 변수에 할당 하는 것과 같습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="83a57-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83a57-113">예제</span><span class="sxs-lookup"><span data-stu-id="83a57-113">Example</span></span>  
 <span data-ttu-id="83a57-114">다음 예제에서는 문을 사용 하 여 `Erase` 두 배열을 지우고 해당 메모리 (1000 및 100 저장소 요소 각각)를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="83a57-115">`ReDim`그런 다음 문이 새 배열 인스턴스를 3 차원 배열에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a57-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="83a57-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83a57-116">See also</span></span>

- [<span data-ttu-id="83a57-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="83a57-117">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="83a57-118">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="83a57-118">ReDim Statement</span></span>](redim-statement.md)
