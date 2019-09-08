---
title: 데이터 세트 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d496167b7bce31491402414c43ae0bcdee423b89
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786501"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="b3100-102">데이터 세트 만들기</span><span class="sxs-lookup"><span data-stu-id="b3100-102">Creating a DataSet</span></span>
<span data-ttu-id="b3100-103"><xref:System.Data.DataSet>의 인스턴스는 <xref:System.Data.DataSet> 생성자를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="b3100-104">선택적으로 이름 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-104">Optionally specify a name argument.</span></span> <span data-ttu-id="b3100-105"><xref:System.Data.DataSet>의 이름을 지정하지 않으면 해당 이름은 "NewDataSet"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="b3100-106">기존 <xref:System.Data.DataSet>을 기반으로 새 <xref:System.Data.DataSet>을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3100-107">새 <xref:System.Data.DataSet>은 기존 <xref:System.Data.DataSet>과 동일한 복사본이거나, 관계 구조 또는 스키마는 복사하지만 기존 <xref:System.Data.DataSet>의 데이터는 포함하지 않는 <xref:System.Data.DataSet>의 복제이거나, 또는 <xref:System.Data.DataSet> 메서드를 사용하여 기존 <xref:System.Data.DataSet>의 수정된 행만 포함하는 <xref:System.Data.DataSet.GetChanges%2A>의 하위 집합일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="b3100-108">자세한 내용은 [데이터 집합 내용 복사](copying-dataset-contents.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3100-108">For more information, see [Copying DataSet Contents](copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="b3100-109">다음 코드 예제에서는 <xref:System.Data.DataSet>의 인스턴스를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3100-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3100-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3100-110">See also</span></span>

- [<span data-ttu-id="b3100-111">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="b3100-111">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="b3100-112">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="b3100-112">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b3100-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b3100-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
