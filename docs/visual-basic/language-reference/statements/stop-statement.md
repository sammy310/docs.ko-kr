---
title: Stop 문
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
ms.openlocfilehash: c9226ccaea9a0709a9d6a49900f69cb9ac9e1dbe
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871747"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="b8b06-102">Stop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8b06-102">Stop Statement (Visual Basic)</span></span>

<span data-ttu-id="b8b06-103">실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b06-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8b06-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8b06-105">설명</span><span class="sxs-lookup"><span data-stu-id="b8b06-105">Remarks</span></span>  

 <span data-ttu-id="b8b06-106">`Stop`프로시저에 문을 추가 하 여 실행을 일시 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="b8b06-107">문을 사용 하는 `Stop` 것은 코드에서 중단점을 설정 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="b8b06-108">`Stop`문은 실행을 일시 중단 하지만,와는 달리 `End` 컴파일된 실행 파일 (.exe)에서 발생 한 경우를 제외 하 고는 파일을 닫지 않거나 모든 변수를 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8b06-109">`Stop`IDE (통합 개발 환경) 외부에서 실행 되는 코드에 문이 있으면 디버거가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="b8b06-110">이는 코드가 디버그 모드에서 컴파일 되었는지 아니면 소매 모드에서 컴파일 되었는지에 관계 없이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8b06-111">예제</span><span class="sxs-lookup"><span data-stu-id="b8b06-111">Example</span></span>  

 <span data-ttu-id="b8b06-112">이 예제에서는 문을 사용 하 여 `Stop` 루프를 통해 반복할 때마다 실행을 일시 중단 `For...Next` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b06-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="b8b06-113">참조</span><span class="sxs-lookup"><span data-stu-id="b8b06-113">See also</span></span>

- [<span data-ttu-id="b8b06-114">End 문</span><span class="sxs-lookup"><span data-stu-id="b8b06-114">End Statement</span></span>](end-statement.md)
