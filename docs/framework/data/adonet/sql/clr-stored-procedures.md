---
title: CLR 저장 프로시저
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 736020695ae40a8884057ddee8aac8abe6e8c1fd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554197"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="b90b6-102">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="b90b6-102">CLR Stored Procedures</span></span>
<span data-ttu-id="b90b6-103">저장 프로시저는 스칼라 식에서 사용할 수 없는 루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="b90b6-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="b90b6-104">또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL(데이터 정의 언어) 및 DML(데이터 조작 언어) 문을 호출하며 출력 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b90b6-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b90b6-105">Microsoft Visual Basic에서는 Microsoft Visual C#과 다른 방식으로 출력 매개 변수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b90b6-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="b90b6-106">다음과 같이 매개 변수를 참조로 전달 하도록 지정 하 고 \<Out()> 특성을 적용 하 여 출력 매개 변수를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90b6-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="b90b6-107">자세한 내용은 사용 중인 SQL Server 버전에 대 한 [SQL Server 설명서](/sql) 의 버전을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b90b6-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="b90b6-108">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="b90b6-108">**SQL Server documentation**</span></span>

1. <span data-ttu-id="b90b6-109">[CLR 저장 프로시저](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="b90b6-109">[CLR Stored Procedures](/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90b6-110">참조</span><span class="sxs-lookup"><span data-stu-id="b90b6-110">See also</span></span>

- <span data-ttu-id="b90b6-111">[관리 코드에서 SQL Server 2005 개체 만들기](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b90b6-111">[Creating SQL Server 2005 Objects In Managed Code](/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="b90b6-112">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b90b6-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
