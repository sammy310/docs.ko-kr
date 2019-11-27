---
title: '방법: 오버로드된 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d983f5f6183c33141079ed35171f7a73f254450f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340204"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="54c4b-102">방법: 오버로드된 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54c4b-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="54c4b-103">프로시저 오버 로드의 이점은 호출의 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="54c4b-104">호출 하는 코드는 프로시저에 전달 하는 데 필요한 정보를 얻은 다음 전달 하는 인수에 관계 없이 단일 프로시저 이름을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="54c4b-105">정의 된 버전이 둘 이상 있는 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="54c4b-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="54c4b-106">호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="54c4b-107">일반적인 방법으로 프로시저 호출을 작성 하 여 인수 목록에 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="54c4b-108">인수는 프로시저에 대해 정의 된 버전 중 하나의 매개 변수 목록과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="54c4b-109">호출할 프로시저 버전을 결정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="54c4b-110">Visual Basic는 인수 목록과 일치 하는 버전으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="54c4b-111">다음 예에서는 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)에서 선언 된 `post` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="54c4b-112">이 서비스는 고객 id를 가져오고 `String` 인지 아니면 `Integer`인지를 결정 한 다음 두 경우 모두 동일한 절차를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="54c4b-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="54c4b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54c4b-113">See also</span></span>

- [<span data-ttu-id="54c4b-114">절차</span><span class="sxs-lookup"><span data-stu-id="54c4b-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="54c4b-115">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="54c4b-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="54c4b-116">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="54c4b-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="54c4b-117">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="54c4b-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="54c4b-118">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="54c4b-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="54c4b-119">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="54c4b-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="54c4b-120">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="54c4b-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="54c4b-121">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="54c4b-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="54c4b-122">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="54c4b-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="54c4b-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="54c4b-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
