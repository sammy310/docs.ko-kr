---
title: DataTable 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 91db42acb0e09b8fc99b0ee710a60800d40938ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112855"
---
# <a name="navigating-datatables"></a><span data-ttu-id="e0dae-102">DataTable 탐색</span><span class="sxs-lookup"><span data-stu-id="e0dae-102">Navigating DataTables</span></span>
<span data-ttu-id="e0dae-103"><xref:System.Data.DataTableReader>는 하나 이상의 <xref:System.Data.DataTable> 개체 내용을 하나 이상의 앞으로만 이동 가능한 읽기 전용 결과 집합 형태로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0dae-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="e0dae-104"><xref:System.Data.DataTableReader> 메서드를 사용하여 <xref:System.Data.DataSet.CreateDataReader%2A>를 만들 경우에는 여러 개의 결과 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0dae-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="e0dae-105">결과 집합이 둘 이상이면 <xref:System.Data.DataTableReader.NextResult%2A> 메서드는 커서를 다음 결과 집합으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0dae-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="e0dae-106">이것은 앞으로만 이동 가능한 프로세스이며,</span><span class="sxs-lookup"><span data-stu-id="e0dae-106">This is a forward-only process.</span></span> <span data-ttu-id="e0dae-107">이전 결과 집합으로 돌아갈 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0dae-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0dae-108">예제</span><span class="sxs-lookup"><span data-stu-id="e0dae-108">Example</span></span>  
 <span data-ttu-id="e0dae-109">다음 예제에서는 `TestConstructor` 메서드 두 개 만듭니다 <xref:System.Data.DataTable> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0dae-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="e0dae-110">이 생성자를 보여 주기 위해 합니다 <xref:System.Data.DataTableReader> 클래스, 예제에서는 새 **DataTableReader** 두 가지를 포함 하는 배열을 기반으로 **Datatable**, 간단한 작업을 수행 콘솔 창에는 처음 몇 개의 열에서 콘텐츠를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0dae-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e0dae-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0dae-111">See also</span></span>

- [<span data-ttu-id="e0dae-112">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="e0dae-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [<span data-ttu-id="e0dae-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="e0dae-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
