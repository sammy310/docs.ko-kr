---
title: DataTable 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148310"
---
# <a name="navigating-datatables"></a><span data-ttu-id="fe095-102">DataTable 탐색</span><span class="sxs-lookup"><span data-stu-id="fe095-102">Navigating DataTables</span></span>

<span data-ttu-id="fe095-103"><xref:System.Data.DataTableReader>는 하나 이상의 <xref:System.Data.DataTable> 개체 내용을 하나 이상의 앞으로만 이동 가능한 읽기 전용 결과 집합 형태로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="fe095-104"><xref:System.Data.DataTableReader> 메서드를 사용하여 <xref:System.Data.DataSet.CreateDataReader%2A>를 만들 경우에는 여러 개의 결과 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="fe095-105">결과 집합이 둘 이상이면 <xref:System.Data.DataTableReader.NextResult%2A> 메서드는 커서를 다음 결과 집합으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="fe095-106">이것은 앞으로만 이동 가능한 프로세스이며,</span><span class="sxs-lookup"><span data-stu-id="fe095-106">This is a forward-only process.</span></span> <span data-ttu-id="fe095-107">이전 결과 집합으로 돌아갈 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe095-108">예제</span><span class="sxs-lookup"><span data-stu-id="fe095-108">Example</span></span>  

 <span data-ttu-id="fe095-109">다음 예제에서 `TestConstructor` 메서드는 두 개의 인스턴스를 <xref:System.Data.DataTable> 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="fe095-110">이 샘플은 클래스에 대 한이 생성자를 보여 주기 위해 <xref:System.Data.DataTableReader> 두 **datatable**포함 된 배열을 기반으로 하는 새 **DataTableReader** 을 만들고 간단한 작업을 수행 하 여 처음 몇 개의 열에서 콘솔 창으로 내용을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe095-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fe095-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe095-111">See also</span></span>

- [<span data-ttu-id="fe095-112">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="fe095-112">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="fe095-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="fe095-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
