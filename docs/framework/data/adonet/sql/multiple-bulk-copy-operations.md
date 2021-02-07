---
description: '자세히 알아보기: 여러 대량 복사 작업'
title: 여러 개의 대량 복사 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: dfc694cfb4a993889bed607be71821bb1f9fddf1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767663"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="fcc9c-103">여러 개의 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="fcc9c-103">Multiple Bulk Copy Operations</span></span>

<span data-ttu-id="fcc9c-104"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스의 단일 인스턴스를 사용하여 여러 대량 복사 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-104">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="fcc9c-105">복사본 간에 작업 매개 변수(예: 대상 테이블의 이름)가 변경되는 경우 다음 예제에 설명된 대로 **WriteToServer** 메서드에 대한 후속 호출 전에 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-105">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="fcc9c-106">명시적으로 변경한 경우가 아니라면 모든 속성 값이 지정된 인스턴스에 대한 이전 대량 복사 작업 시와 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-106">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcc9c-107"><xref:System.Data.SqlClient.SqlBulkCopy>의 동일한 인스턴스를 사용하여 여러 대량 복사 작업을 수행하면 일반적으로 각 작업에 대해 별도의 인스턴스를 사용하는 경우보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-107">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="fcc9c-108">동일한 <xref:System.Data.SqlClient.SqlBulkCopy> 개체를 사용하여 여러 대량 복사 작업을 수행하는 경우 원본 또는 대상 정보가 각 작업에서 동일한지 다른지에 대한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-108">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="fcc9c-109">그러나 서버에 쓸 때마다 열 연결 정보가 제대로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-109">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fcc9c-110">[대량 복사 예제 설정](bulk-copy-example-setup.md)에 설명 된 대로 작업 테이블을 만들지 않은 경우이 샘플은 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-110">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="fcc9c-111">이 코드는 **SqlBulkCopy** 를 사용하는 구문을 보여 주는 용도로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-111">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="fcc9c-112">원본 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9c-112">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fcc9c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcc9c-113">See also</span></span>

- [<span data-ttu-id="fcc9c-114">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="fcc9c-114">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="fcc9c-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="fcc9c-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
