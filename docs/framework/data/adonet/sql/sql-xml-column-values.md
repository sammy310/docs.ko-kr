---
description: '자세한 정보: SQL XML 열 값'
title: SQL XML 열 값
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 357d55e2ce497c9929b8e7e7459ebf23ccaafede
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767182"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="91c2c-103">SQL XML 열 값</span><span class="sxs-lookup"><span data-stu-id="91c2c-103">SQL XML Column Values</span></span>

<span data-ttu-id="91c2c-104">SQL Server에서는 `xml` 데이터 형식을 지원하므로 개발자가 <xref:System.Data.SqlClient.SqlCommand> 클래스의 표준 동작을 사용하여 이 형식이 포함된 결과 집합을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-104">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="91c2c-105">`xml` 열은 다른 열과 같은 방식으로 검색할 수 있지만(예: <xref:System.Data.SqlClient.SqlDataReader>) 열의 콘텐츠를 XML로 활용하려면 <xref:System.Xml.XmlReader>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-105">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c2c-106">예제</span><span class="sxs-lookup"><span data-stu-id="91c2c-106">Example</span></span>  

 <span data-ttu-id="91c2c-107">다음 콘솔 애플리케이션에서는 `xml`AdventureWorks **데이터베이스의** Sales.Store **테이블에서** 인스턴스까지 각각 <xref:System.Data.SqlClient.SqlDataReader> 열이 포함된 두 개의 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-107">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="91c2c-108">각 행에 대해 `xml`의 <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 메서드를 사용하여 <xref:System.Data.SqlClient.SqlDataReader> 열의 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-108">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="91c2c-109">이 값은 <xref:System.Xml.XmlReader>에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-109">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="91c2c-110"><xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>는 <xref:System.Data.IDataRecord.GetValue%2A> 열의 값을 문자열로 반환하므로 콘텐츠를 <xref:System.Data.SqlTypes.SqlXml> 변수로 설정하려면 <xref:System.Data.IDataRecord.GetValue%2A> 메서드가 아닌 `xml`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-110">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91c2c-111">**AdventureWorks** 샘플 데이터베이스는 SQL Server를 설치할 때 기본적으로 설치되지 않으며</span><span class="sxs-lookup"><span data-stu-id="91c2c-111">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="91c2c-112">SQL Server Setup을 실행하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91c2c-112">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="91c2c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91c2c-113">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="91c2c-114">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="91c2c-114">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="91c2c-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="91c2c-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
