---
title: '방법: 개체 변수가 인스턴스를 참조 하지 않도록 설정 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004910"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="cf9ac-102">방법: 개체 변수가 인스턴스를 참조 하지 않도록 설정 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf9ac-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="cf9ac-103">개체 변수를 [Nothing](../../../../visual-basic/language-reference/nothing.md)으로 설정 하 여 개체 인스턴스의 연관을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="cf9ac-104">개체 인스턴스에서 개체 변수를 분리 하려면</span><span class="sxs-lookup"><span data-stu-id="cf9ac-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="cf9ac-105">대입문에서 변수를 `Nothing`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="cf9ac-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cf9ac-106">Robust Programming</span></span>  
 <span data-ttu-id="cf9ac-107">코드에서 `Nothing`으로 설정 된 개체 변수의 멤버에 액세스 하려고 하면 <xref:System.NullReferenceException>이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="cf9ac-108">개체 변수를 `Nothing`으로 자주 설정 하거나 변수가 초기화 되지 않은 경우 `Try...Catch...Finally` 블록에 멤버 액세스를 묶는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cf9ac-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="cf9ac-109">.NET Framework Security</span></span>  
 <span data-ttu-id="cf9ac-110">기밀 데이터 나 중요 한 데이터가 포함 된 개체에 개체 변수를 사용 하는 경우 해당 개체 중 하나를 적극적으로 처리 하지 않을 때 변수를 `Nothing`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="cf9ac-111">이렇게 하면 악의적인 코드가 데이터에 액세스 하는 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9ac-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9ac-112">참조</span><span class="sxs-lookup"><span data-stu-id="cf9ac-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="cf9ac-113">개체 변수</span><span class="sxs-lookup"><span data-stu-id="cf9ac-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="cf9ac-114">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="cf9ac-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="cf9ac-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="cf9ac-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="cf9ac-116">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="cf9ac-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
