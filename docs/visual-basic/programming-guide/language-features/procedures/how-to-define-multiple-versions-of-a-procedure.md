---
title: '방법: 여러 버전의 프로시저 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: e8ed9a6356b7177b2c029a9280d0790a93676653
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347592"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="32da5-102">방법: 여러 버전의 프로시저 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32da5-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="32da5-103">각 버전에 대해 동일한 이름을 사용 하 고 다른 매개 변수 목록을 사용 *하 여 프로시저* 를 여러 버전으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="32da5-104">오버 로드의 목적은 프로시저를 이름으로 구분 하지 않고도 긴밀 하 게 관련 된 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="32da5-105">자세한 내용은 [Procedure Overloading](./procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32da5-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="32da5-106">프로시저의 여러 버전을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="32da5-106">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="32da5-107">정의 하려는 프로시저의 각 버전에 대 한 `Sub` 또는 `Function` 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="32da5-108">모든 선언에 동일한 프로시저 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-108">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="32da5-109">각 선언의 `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="32da5-110">필요에 따라 선언에서 `Overloads` 생략할 수 있지만 선언에 포함 하는 경우 모든 선언에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="32da5-111">각 선언 문 다음에 호출 코드가 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 특정 사례를 처리 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="32da5-112">호출 코드에서 제공 하는 매개 변수를 테스트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="32da5-113">Visual Basic는 프로시저의 일치 하는 버전으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="32da5-114">`End Sub` 또는 `End Function` 문을 사용 하 여 프로시저의 각 버전을 적절 하 게 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32da5-115">예</span><span class="sxs-lookup"><span data-stu-id="32da5-115">Example</span></span>  
 <span data-ttu-id="32da5-116">다음 예에서는 고객의 잔액에 대해 트랜잭션을 게시 하는 `Sub` 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="32da5-117">`Overloads` 키워드를 사용 하 여 두 가지 버전의 프로시저를 정의 합니다. 하나는 이름으로 고객을 수락 하 고 다른 하나는 계정 번호로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="32da5-118">호출 코드는 고객 id를 `String` 또는 `Integer`으로 가져온 다음 두 경우 모두 동일한 호출 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="32da5-119">이러한 버전의 `post` 프로시저를 호출 하는 방법에 대 한 자세한 내용은 [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32da5-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="32da5-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="32da5-120">Compile the code</span></span>  
 <span data-ttu-id="32da5-121">오버 로드 된 각 버전에 동일한 프로시저 이름이 있지만 다른 매개 변수 목록이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da5-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32da5-122">참조</span><span class="sxs-lookup"><span data-stu-id="32da5-122">See also</span></span>

- [<span data-ttu-id="32da5-123">절차</span><span class="sxs-lookup"><span data-stu-id="32da5-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="32da5-124">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="32da5-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32da5-125">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="32da5-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="32da5-126">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="32da5-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="32da5-127">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="32da5-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="32da5-128">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="32da5-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="32da5-129">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="32da5-129">Overload Resolution</span></span>](./overload-resolution.md)
