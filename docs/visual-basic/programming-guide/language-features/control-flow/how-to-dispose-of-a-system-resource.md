---
title: '방법: Dispose 시스템 리소스 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: e3594db036edc3a6288b0373737c1ee26a691a57
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906739"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="8e82e-102">방법: Dispose 시스템 리소스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e82e-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="8e82e-103">사용할 수는 `Using` 코드 블록을 종료할 때 시스템 리소스의 삭제를 보장 하기 위해 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="8e82e-104">많은 양의 메모리를 사용 하는 다른 구성 요소는 또한 사용 하려는 또는 시스템 리소스를 사용 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="8e82e-105">코드 작업을 마쳤을 때 데이터베이스 연결을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="8e82e-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="8e82e-106">적절 한 포함 되어 있는지 확인 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 소스 파일의 시작 부분에 데이터베이스 연결에 대 한 (이 예제의 경우 <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="8e82e-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="8e82e-107">만들기는 `Using` 블록을 `Using` 및 `End Using` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="8e82e-108">블록 내의 데이터베이스 연결을 사용 하 여 처리 하는 코드를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="8e82e-109">연결을 선언 하 고의 일부로 해당 인스턴스를 만들어야 합니다 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="8e82e-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="8e82e-110">시스템 처리 되지 않은 예외의 경우를 포함 하 여 블록을 종료 하는 방법에 관계 없이 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="8e82e-111">액세스할 수 없는 참고 `sqc` 에서 외부는 `Using` 해당 범위는 블록으로 제한 되기 때문에 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="8e82e-112">COM 래퍼 파일 핸들 등의 시스템 리소스에 동일한 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e82e-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="8e82e-113">사용 하는 `Using` 블록을 종료 한 후 다른 구성 요소에 대 한 사용 가능한 리소스 되도록 하려는 경우는 `Using` 블록.</span><span class="sxs-lookup"><span data-stu-id="8e82e-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e82e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e82e-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="8e82e-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="8e82e-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="8e82e-116">판단 구조</span><span class="sxs-lookup"><span data-stu-id="8e82e-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="8e82e-117">루프 구조</span><span class="sxs-lookup"><span data-stu-id="8e82e-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="8e82e-118">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="8e82e-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="8e82e-119">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="8e82e-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="8e82e-120">Using 문</span><span class="sxs-lookup"><span data-stu-id="8e82e-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
