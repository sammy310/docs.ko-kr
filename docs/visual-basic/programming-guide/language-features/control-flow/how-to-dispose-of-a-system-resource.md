---
description: '자세한 정보: 방법: 시스템 리소스 삭제 (Visual Basic)'
title: '방법: 시스템 리소스 삭제'
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
ms.openlocfilehash: 6594c9e2eedf756cc7a46c2c17deab58fcba3a8c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480663"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="41381-103">방법: 시스템 리소스 해제(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41381-103">How to: Dispose of a System Resource (Visual Basic)</span></span>

<span data-ttu-id="41381-104">블록을 사용 하면 `Using` 코드가 블록을 종료할 때 시스템에서 리소스를 삭제 하는 것을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41381-104">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="41381-105">이는 많은 양의 메모리를 사용 하는 시스템 리소스를 사용 하는 경우 나 다른 구성 요소 에서도를 사용 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41381-105">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="41381-106">코드가 완료 될 때 데이터베이스 연결을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="41381-106">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="41381-107">소스 파일 (이 경우)의 시작 부분에 데이터베이스 연결에 대 한 적절 한 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) 이 포함 되어 있는지 확인 <xref:System.Data.SqlClient> 합니다.</span><span class="sxs-lookup"><span data-stu-id="41381-107">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="41381-108">`Using`및 문을 사용 하 여 블록을 만듭니다 `Using` `End Using` .</span><span class="sxs-lookup"><span data-stu-id="41381-108">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="41381-109">블록 내에서 데이터베이스 연결을 처리 하는 코드를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="41381-109">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="41381-110">연결을 선언 하 고 문의 일부로이의 인스턴스를 만듭니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="41381-110">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="41381-111">처리 되지 않은 예외의 경우를 비롯 하 여 블록을 종료 하는 방법에 관계 없이 시스템에서 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="41381-111">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="41381-112">`sqc` `Using` 블록의 범위는 블록으로 제한 되기 때문에 블록 외부에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41381-112">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="41381-113">이 동일한 기술을 파일 핸들, COM 래퍼 등의 시스템 리소스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41381-113">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="41381-114">`Using`블록을 종료 한 후에 다른 구성 요소에서 리소스를 사용할 수 있도록 하려는 경우 블록을 사용 `Using` 합니다.</span><span class="sxs-lookup"><span data-stu-id="41381-114">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41381-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="41381-115">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="41381-116">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="41381-116">Control Flow</span></span>](index.md)
- [<span data-ttu-id="41381-117">판단 구조체</span><span class="sxs-lookup"><span data-stu-id="41381-117">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="41381-118">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="41381-118">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="41381-119">기타 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="41381-119">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="41381-120">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="41381-120">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="41381-121">Using 문</span><span class="sxs-lookup"><span data-stu-id="41381-121">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
