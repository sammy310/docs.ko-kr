---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785349"
---
# <a name="datatablereaders"></a><span data-ttu-id="32cd8-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="32cd8-102">DataTableReaders</span></span>
<span data-ttu-id="32cd8-103"><xref:System.Data.DataTableReader>는 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용을 하나 이상의 정방향 읽기 전용 결과 집합 형태로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="32cd8-104">**Datatable**에서 **DataTableReader** 를 만들 때 결과 **DataTableReader** 개체에는로 표시 된 행을 제외 하 고 생성 된 **datatable** 과 동일한 데이터가 포함 된 결과 집합이 하나 포함 됩니다. deleted.</span><span class="sxs-lookup"><span data-stu-id="32cd8-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="32cd8-105">열은 원래 **DataTable**과 동일한 순서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="32cd8-106">을 호출 <xref:System.Data.DataSet.CreateDataReader%2A>하 여 생성 된 경우 DataTableReader에는 여러 개의 결과 집합이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="32cd8-107">결과는 **DataSet** 개체의 <xref:System.Data.DataSet.Tables%2A> 컬렉션에 있는 **datatable** 의 순서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32cd8-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="32cd8-108">In This Section</span></span>  
 [<span data-ttu-id="32cd8-109">DataReader 만들기</span><span class="sxs-lookup"><span data-stu-id="32cd8-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="32cd8-110">**DataTableReader** 개체를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="32cd8-111">DataTable 탐색</span><span class="sxs-lookup"><span data-stu-id="32cd8-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="32cd8-112">**Read** 메서드를 사용 하 여 **DataTableReader**의 콘텐츠를 이동 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cd8-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cd8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="32cd8-113">See also</span></span>

- [<span data-ttu-id="32cd8-114">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="32cd8-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="32cd8-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="32cd8-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
