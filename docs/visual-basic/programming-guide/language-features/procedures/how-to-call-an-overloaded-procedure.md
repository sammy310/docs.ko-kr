---
title: '방법: 오버 로드 된 프로시저 호출 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d325c09516b4ce03facedce86f17ea49480b997a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317813"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="e62e3-102">방법: 오버 로드 된 프로시저 호출 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e62e3-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="e62e3-103">프로시저 오버 로드의 장점은 호출의 유연한입니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="e62e3-104">호출 코드를 프로시저에 전달 하 고 단일 프로시저 이름을 전달 하는 어떤 인수 없이 호출 하는 데 필요한 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="e62e3-105">정의 된 버전이 둘 이상 있는 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="e62e3-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="e62e3-106">호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="e62e3-107">프로시저 호출 인수 목록의 데이터를 표시 합니다. 일반적인 방법으로 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="e62e3-108">인수는 프로시저에 정의 된 버전 중 하나에 매개 변수 목록과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="e62e3-109">호출 프로시저의 버전을 확인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="e62e3-110">Visual Basic에서 인수 목록과 일치 하는 버전 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="e62e3-111">다음 예제에서는 합니다 `post` 프로시저에서 선언 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="e62e3-112">고객 id를 받아 인지 여부를 확인을 `String` 또는 `Integer`, 한 다음 두 경우 모두 같은 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62e3-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="e62e3-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e62e3-113">See also</span></span>

- [<span data-ttu-id="e62e3-114">절차</span><span class="sxs-lookup"><span data-stu-id="e62e3-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e62e3-115">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="e62e3-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e62e3-116">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="e62e3-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="e62e3-117">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e62e3-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="e62e3-118">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="e62e3-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="e62e3-119">방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="e62e3-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="e62e3-120">방법: 무한 개수의 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="e62e3-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="e62e3-121">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="e62e3-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="e62e3-122">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="e62e3-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="e62e3-123">오버로드</span><span class="sxs-lookup"><span data-stu-id="e62e3-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
