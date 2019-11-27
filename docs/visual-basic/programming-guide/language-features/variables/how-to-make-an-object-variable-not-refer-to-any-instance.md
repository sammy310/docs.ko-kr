---
title: '방법: 개체 변수가 인스턴스를 참조하지 않도록 설정'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352890"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="022ef-102">방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="022ef-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="022ef-103">개체 변수를 [Nothing](../../../../visual-basic/language-reference/nothing.md)으로 설정 하 여 개체 인스턴스의 연관을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="022ef-104">개체 인스턴스에서 개체 변수를 분리 하려면</span><span class="sxs-lookup"><span data-stu-id="022ef-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="022ef-105">대입문에서 변수를 `Nothing` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="022ef-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="022ef-106">Robust Programming</span></span>  
 <span data-ttu-id="022ef-107">코드가 `Nothing`로 설정 된 개체 변수의 멤버에 액세스 하려고 하면 <xref:System.NullReferenceException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="022ef-108">개체 변수를 자주 `Nothing` 설정 하거나 변수가 초기화 되지 않은 경우 멤버 액세스를 `Try...Catch...Finally` 블록에 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="022ef-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="022ef-109">.NET Framework Security</span></span>  
 <span data-ttu-id="022ef-110">기밀 데이터 나 중요 한 데이터가 포함 된 개체에 대해 개체 변수를 사용 하는 경우 해당 개체 중 하나를 사용 하 여 적극적으로 처리 하지 않을 때 변수를 `Nothing` 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="022ef-111">이렇게 하면 악의적인 코드가 데이터에 액세스 하는 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022ef-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="022ef-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="022ef-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="022ef-113">개체 변수</span><span class="sxs-lookup"><span data-stu-id="022ef-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="022ef-114">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="022ef-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="022ef-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="022ef-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="022ef-116">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="022ef-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
