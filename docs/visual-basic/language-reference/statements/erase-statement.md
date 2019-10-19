---
title: Erase 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583394"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="b46be-102">Erase 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b46be-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="b46be-103">배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리의 할당을 취소 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46be-104">구문</span><span class="sxs-lookup"><span data-stu-id="b46be-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="b46be-105">요소</span><span class="sxs-lookup"><span data-stu-id="b46be-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="b46be-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b46be-106">Required.</span></span> <span data-ttu-id="b46be-107">지울 배열 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-107">List of array variables to be erased.</span></span> <span data-ttu-id="b46be-108">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b46be-109">주의</span><span class="sxs-lookup"><span data-stu-id="b46be-109">Remarks</span></span>  
 <span data-ttu-id="b46be-110">@No__t_0 문은 프로시저 수준 에서만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="b46be-111">즉, 프로시저 내에서 배열을 해제할 수 있지만 클래스 또는 모듈 수준에서는 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="b46be-112">@No__t_0 문은 각 배열 변수에 `Nothing`를 할당 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b46be-113">예제</span><span class="sxs-lookup"><span data-stu-id="b46be-113">Example</span></span>  
 <span data-ttu-id="b46be-114">다음 예에서는 `Erase` 문을 사용 하 여 두 배열을 지우고 해당 메모리 (1000 및 100 저장소 요소 각각)를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="b46be-115">그런 다음 `ReDim` 문은 3 차원 배열에 새 배열 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46be-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="b46be-116">참조</span><span class="sxs-lookup"><span data-stu-id="b46be-116">See also</span></span>

- [<span data-ttu-id="b46be-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="b46be-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="b46be-118">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="b46be-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
