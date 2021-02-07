---
description: SqlTypes 및 데이터 집합에 대해 자세히 알아보세요.
title: SqlType 및 DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 088c1cdc65b3c79a77e0bf724b5550c001a40554
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767000"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="449f3-103">SqlType 및 DataSet</span><span class="sxs-lookup"><span data-stu-id="449f3-103">SqlTypes and the DataSet</span></span>

<span data-ttu-id="449f3-104">ADO.NET 2.0은 <xref:System.Data.SqlTypes> 네임스페이스를 통해 `DataSet`에 대해 강화된 형식 지원을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-104">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="449f3-105"><xref:System.Data.SqlTypes>의 형식은 SQL Server 데이터베이스의 데이터 형식과 의미 체계 및 정밀도가 동일한 데이터 형식을 제공하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-105">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="449f3-106"><xref:System.Data.SqlTypes>의 각 데이터 형식은 SQL Server의 데이터 형식과 동일하며 기본 데이터 표현도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-106">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="449f3-107">SQL Server data 형식을 사용할 때 <xref:System.Data.DataSet>에서 직접 <xref:System.Data.SqlTypes>를 사용하면 다양한 혜택이 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-107">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="449f3-108"><xref:System.Data.SqlTypes>는 SQL Server 기본 데이터 형식과 동일한 의미 체계를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-108"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="449f3-109"><xref:System.Data.DataColumn>의 정의에서 <xref:System.Data.SqlTypes> 중 하나를 지정하면 10진 또는 숫자 데이터 형식을 공용 언어 런타임(CLR) 데이터 형식으로 변환할 때 발생할 수 있는 정확도 손실이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-109">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="449f3-110">예제</span><span class="sxs-lookup"><span data-stu-id="449f3-110">Example</span></span>  

 <span data-ttu-id="449f3-111">다음 예지에서는 <xref:System.Data.DataTable> 개체를 만들고 CLR 형식 대신 <xref:System.Data.SqlTypes>를 사용하여 <xref:System.Data.DataColumn> 데이터 형식을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-111">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="449f3-112">이 코드는 SQL Server의 AdventureWorks 데이터베이스에 있는 Sales.SalesOrderDetail 테이블의 데이터로 <xref:System.Data.DataTable>을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-112">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="449f3-113">콘솔 창에 표시되는 출력은 각 열의 데이터 형식과 SQL Server에서 검색된 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="449f3-113">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="449f3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="449f3-114">See also</span></span>

- [<span data-ttu-id="449f3-115">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="449f3-115">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="449f3-116">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="449f3-116">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="449f3-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="449f3-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
