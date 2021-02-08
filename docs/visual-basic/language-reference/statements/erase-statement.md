---
description: '자세한 정보: Erase 문 (Visual Basic)'
title: Erase 문
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 295abec89f3d69f8f2641a5a3d574a2d10f98474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769158"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="eb637-103">Erase 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb637-103">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="eb637-104">배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리의 할당을 취소 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-104">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb637-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb637-105">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="eb637-106">부분</span><span class="sxs-lookup"><span data-stu-id="eb637-106">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="eb637-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-107">Required.</span></span> <span data-ttu-id="eb637-108">지울 배열 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-108">List of array variables to be erased.</span></span> <span data-ttu-id="eb637-109">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-109">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb637-110">설명</span><span class="sxs-lookup"><span data-stu-id="eb637-110">Remarks</span></span>  

 <span data-ttu-id="eb637-111">`Erase`문은 프로시저 수준 에서만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-111">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="eb637-112">즉, 프로시저 내에서 배열을 해제할 수 있지만 클래스 또는 모듈 수준에서는 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-112">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="eb637-113">`Erase`문은 각 배열 변수에 할당 하는 것과 같습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="eb637-113">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb637-114">예제</span><span class="sxs-lookup"><span data-stu-id="eb637-114">Example</span></span>  

 <span data-ttu-id="eb637-115">다음 예제에서는 문을 사용 하 여 `Erase` 두 배열을 지우고 해당 메모리 (1000 및 100 저장소 요소 각각)를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-115">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="eb637-116">`ReDim`그런 다음 문이 새 배열 인스턴스를 3 차원 배열에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb637-116">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="eb637-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb637-117">See also</span></span>

- [<span data-ttu-id="eb637-118">Nothing</span><span class="sxs-lookup"><span data-stu-id="eb637-118">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="eb637-119">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="eb637-119">ReDim Statement</span></span>](redim-statement.md)
