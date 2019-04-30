---
title: '방법: ADO.NET 명령 및 DataContext 간의 연결 다시 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 47e1e45cfe693e3569c343f1058ce2d610af96dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033698"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="f090e-102">방법: ADO.NET 명령 및 DataContext 간의 연결 다시 사용</span><span class="sxs-lookup"><span data-stu-id="f090e-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="f090e-103">때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 의 일부인 합니다 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 기술 제품군의 제공 하는 서비스를 기반으로 하 고 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], 간의 연결을 다시 사용할 수 있습니다는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령 및 <xref:System.Data.Linq.DataContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="f090e-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f090e-104">예제</span><span class="sxs-lookup"><span data-stu-id="f090e-104">Example</span></span>  
 <span data-ttu-id="f090e-105">다음 예제에서는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령과 <xref:System.Data.Linq.DataContext> 간에 동일한 연결을 다시 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f090e-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f090e-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="f090e-106">See also</span></span>

- [<span data-ttu-id="f090e-107">배경 정보</span><span class="sxs-lookup"><span data-stu-id="f090e-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="f090e-108">ADO.NET 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f090e-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="f090e-109">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="f090e-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
