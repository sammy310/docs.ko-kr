---
title: Stop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827993"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="b9511-102">Stop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9511-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="b9511-103">실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9511-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9511-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9511-105">설명</span><span class="sxs-lookup"><span data-stu-id="b9511-105">Remarks</span></span>  
 <span data-ttu-id="b9511-106">배치할 수 있습니다 `Stop` 어디서 나 실행을 일시 중단 하는 절차에에서는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="b9511-107">사용 하 여 `Stop` 문을 코드에 중단점을 설정 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="b9511-108">합니다 `Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에 없는 경우 변수를 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9511-109">경우는 `Stop` 통합된 개발 환경 (IDE) 외부에서 실행 되는 코드에서 문이, 디버거가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="b9511-110">코드 디버그 또는 정식 버전 모드로 컴파일된 여부에 관계 없이 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9511-111">예제</span><span class="sxs-lookup"><span data-stu-id="b9511-111">Example</span></span>  
 <span data-ttu-id="b9511-112">이 예제에서는 합니다 `Stop` 각 반복에 대 한 실행을 일시 중단 하는 문을 `For...Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9511-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="b9511-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b9511-113">See also</span></span>

- [<span data-ttu-id="b9511-114">End 문</span><span class="sxs-lookup"><span data-stu-id="b9511-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
