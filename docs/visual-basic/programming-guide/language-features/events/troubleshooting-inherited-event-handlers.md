---
title: Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053810"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="6f904-102">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6f904-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="6f904-103">이 항목에서는 상속 된 구성 요소에서 이벤트 처리기를 사용 하 여 발생 하는 일반적인 문제를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f904-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6f904-104">절차</span><span class="sxs-lookup"><span data-stu-id="6f904-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="6f904-105">이벤트 처리기의 코드는 모든 호출에 대 한 두 번 실행</span><span class="sxs-lookup"><span data-stu-id="6f904-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="6f904-106">상속 된 이벤트 처리기를 포함할 수 없습니다는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절.</span><span class="sxs-lookup"><span data-stu-id="6f904-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="6f904-107">기본 클래스의 메서드 이벤트와 이미 연결 되어 있으며 그에 따라 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f904-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="6f904-108">제거 된 `Handles` 상속 된 메서드에서 절.</span><span class="sxs-lookup"><span data-stu-id="6f904-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="6f904-109">상속 된 메서드에 없는 경우는 `Handles` 키워드를 추가 코드는 포함 되지 않았는지 확인 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 또는 동일한 이벤트를 처리 하는 추가 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f904-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f904-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f904-110">See also</span></span>

- [<span data-ttu-id="6f904-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="6f904-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
