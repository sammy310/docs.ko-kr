---
description: '자세히 알아보기: 데이터 집합 만들기'
title: 데이터 세트 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 7a52c6e73b5ab3ba4bf384d6bab3640b85929fcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739653"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="eae84-103">데이터 세트 만들기</span><span class="sxs-lookup"><span data-stu-id="eae84-103">Creating a DataSet</span></span>

<span data-ttu-id="eae84-104"><xref:System.Data.DataSet>의 인스턴스는 <xref:System.Data.DataSet> 생성자를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-104">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="eae84-105">선택적으로 이름 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-105">Optionally specify a name argument.</span></span> <span data-ttu-id="eae84-106"><xref:System.Data.DataSet>의 이름을 지정하지 않으면 해당 이름은 "NewDataSet"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-106">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="eae84-107">기존 <xref:System.Data.DataSet>을 기반으로 새 <xref:System.Data.DataSet>을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-107">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="eae84-108">새 <xref:System.Data.DataSet>은 기존 <xref:System.Data.DataSet>과 동일한 복사본이거나, 관계 구조 또는 스키마는 복사하지만 기존 <xref:System.Data.DataSet>의 데이터는 포함하지 않는 <xref:System.Data.DataSet>의 복제이거나, 또는 <xref:System.Data.DataSet> 메서드를 사용하여 기존 <xref:System.Data.DataSet>의 수정된 행만 포함하는 <xref:System.Data.DataSet.GetChanges%2A>의 하위 집합일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-108">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="eae84-109">자세한 내용은 [데이터 집합 내용 복사](copying-dataset-contents.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eae84-109">For more information, see [Copying DataSet Contents](copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="eae84-110">다음 코드 예제에서는 <xref:System.Data.DataSet>의 인스턴스를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eae84-110">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="eae84-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eae84-111">See also</span></span>

- [<span data-ttu-id="eae84-112">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="eae84-112">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="eae84-113">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="eae84-113">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="eae84-114">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="eae84-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
