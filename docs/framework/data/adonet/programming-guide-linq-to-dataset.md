---
title: 프로그래밍 가이드(LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: dc13af06cf6c439d739d76904f206ebc50ba3187
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634809"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="d01ce-102">프로그래밍 가이드(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d01ce-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="d01ce-103">이 섹션에서는 LINQ to DataSet 프로그래밍에 대 한 개념 정보 및 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d01ce-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d01ce-104">In This Section</span></span>  
 [<span data-ttu-id="d01ce-105">LINQ to DataSet의 쿼리</span><span class="sxs-lookup"><span data-stu-id="d01ce-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-106">LINQ to DataSet 쿼리를 작성 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="d01ce-107">데이터 세트 쿼리</span><span class="sxs-lookup"><span data-stu-id="d01ce-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-108"><xref:System.Data.DataSet> 개체를 쿼리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="d01ce-109">DataRow 비교</span><span class="sxs-lookup"><span data-stu-id="d01ce-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-110"><xref:System.Data.DataRowComparer> 개체를 사용하여 데이터 행을 비교하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="d01ce-111">쿼리에서 DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="d01ce-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-112"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드를 사용 하 여 LINQ to DataSet 쿼리에서 <xref:System.Data.DataTable>을 만드는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="d01ce-113">방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable\<T > 구현</span><span class="sxs-lookup"><span data-stu-id="d01ce-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="d01ce-114">제네릭 매개 변수 T가 `CopyToDataTable<T>` 형식이 아닌 사용자 지정 <xref:System.Data.DataRow> 메서드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="d01ce-115">제네릭 Field 및 SetField 메서드</span><span class="sxs-lookup"><span data-stu-id="d01ce-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-116">제네릭 <xref:System.Data.DataRowExtensions.Field%2A> 및 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="d01ce-117">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d01ce-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-118"><xref:System.Data.DataView> 개체를 사용한 데이터 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="d01ce-119">LINQ to DataSet 쿼리 디버깅</span><span class="sxs-lookup"><span data-stu-id="d01ce-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="d01ce-120">LINQ to DataSet 쿼리를 디버깅 하 고 문제를 해결 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="d01ce-121">Security</span><span class="sxs-lookup"><span data-stu-id="d01ce-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="d01ce-122">LINQ to DataSet의 보안 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="d01ce-123">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="d01ce-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="d01ce-124">LINQ 연산자를 사용하는 쿼리 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d01ce-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d01ce-125">참조</span><span class="sxs-lookup"><span data-stu-id="d01ce-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="d01ce-126">참조</span><span class="sxs-lookup"><span data-stu-id="d01ce-126">See also</span></span>

- [<span data-ttu-id="d01ce-127">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d01ce-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="d01ce-128">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="d01ce-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
