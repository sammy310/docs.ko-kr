---
description: '자세히 알아보기: DataReader 만들기'
title: DataReader 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3a9f47ce90beaa3da4c2835f8b75e770a6179a9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725105"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="202b6-103">DataReader 만들기</span><span class="sxs-lookup"><span data-stu-id="202b6-103">Creating a DataReader</span></span>

<span data-ttu-id="202b6-104"><xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스에는 <xref:System.Data.DataTable.CreateDataReader%2A>의 내용이나 <xref:System.Data.DataTable> 개체의 <xref:System.Data.DataSet> 컬렉션 내용을 하나 이상의 정방향 읽기 전용 커서로 반환하는 <xref:System.Data.DataSet.Tables%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202b6-104">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="202b6-105">예제</span><span class="sxs-lookup"><span data-stu-id="202b6-105">Example</span></span>  

 <span data-ttu-id="202b6-106">다음 콘솔 애플리케이션에서는 <xref:System.Data.DataTable> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="202b6-106">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="202b6-107">그런 다음이 예제에서는 메서드를 호출 하는 프로시저에 채워진를 전달 합니다 <xref:System.Data.DataTable> .이 프로시저는 내에 포함 된 <xref:System.Data.DataTable.CreateDataReader%2A> 결과를 반복 합니다 <xref:System.Data.DataTableReader> .</span><span class="sxs-lookup"><span data-stu-id="202b6-107">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="202b6-108">이 예제에서는 콘솔 창에 다음 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="202b6-108">The example displays the following output in the console window:</span></span>  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="202b6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="202b6-109">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="202b6-110">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="202b6-110">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="202b6-111">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="202b6-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
