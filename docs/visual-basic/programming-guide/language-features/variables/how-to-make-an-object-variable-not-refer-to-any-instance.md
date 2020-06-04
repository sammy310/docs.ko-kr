---
title: '방법: 개체 변수가 인스턴스를 참조하지 않도록 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410453"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="c69d5-102">방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c69d5-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="c69d5-103">개체 변수를 [Nothing](../../../language-reference/nothing.md)으로 설정 하 여 개체 인스턴스의 연관을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69d5-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="c69d5-104">개체 인스턴스에서 개체 변수를 분리 하려면</span><span class="sxs-lookup"><span data-stu-id="c69d5-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="c69d5-105">대입문에서 변수를로 설정 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c69d5-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="c69d5-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c69d5-106">Robust Programming</span></span>  
 <span data-ttu-id="c69d5-107">코드가로 설정 된 개체 변수의 멤버에 액세스 하려고 하면이 `Nothing` <xref:System.NullReferenceException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c69d5-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="c69d5-108">개체 변수를 자주로 설정 `Nothing` 하거나 변수가 초기화 되지 않은 경우에는 멤버 액세스를 블록에 포함 하는 것이 좋습니다 `Try...Catch...Finally` .</span><span class="sxs-lookup"><span data-stu-id="c69d5-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c69d5-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="c69d5-109">.NET Framework Security</span></span>  
 <span data-ttu-id="c69d5-110">기밀 데이터 나 중요 한 데이터가 포함 된 개체에 대해 개체 변수를 사용 하는 경우 `Nothing` 해당 개체 중 하나를 적극적으로 처리 하지 않을 때 변수를로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69d5-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="c69d5-111">이렇게 하면 악의적인 코드가 데이터에 액세스 하는 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c69d5-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69d5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c69d5-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="c69d5-113">개체 변수</span><span class="sxs-lookup"><span data-stu-id="c69d5-113">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="c69d5-114">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="c69d5-114">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="c69d5-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="c69d5-115">Nothing</span></span>](../../../language-reference/nothing.md)
- [<span data-ttu-id="c69d5-116">Try...Catch...Finally 명령문</span><span class="sxs-lookup"><span data-stu-id="c69d5-116">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
