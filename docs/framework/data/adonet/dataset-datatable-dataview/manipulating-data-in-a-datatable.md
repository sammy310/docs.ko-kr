---
title: DataTable에서 데이터 조작
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: 96be67859d9fd136d7ad370ae06d9fcf33426f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202575"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="5da54-102">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="5da54-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="5da54-103"><xref:System.Data.DataTable>에서 <xref:System.Data.DataSet>을 만든 후에는 데이터베이스에서 테이블을 사용할 때와 동일하게 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="5da54-104">테이블에서 데이터를 추가, 확인, 편집 및 삭제하고, 오류 및 이벤트를 모니터링하며, 테이블에서 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="5da54-105">데이터를 수정 하는 경우는 **DataTable**, 변경 내용을 정확 하 게 하며 프로그래밍 방식으로 받아들이거나 변경 내용을 거부할 것인지 결정 하는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5da54-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5da54-106">In This Section</span></span>  
 [<span data-ttu-id="5da54-107">DataTable에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="5da54-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="5da54-108">새 행을 만들어 테이블에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="5da54-109">DataTable에서 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="5da54-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="5da54-110">원래 버전과 현재 버전의 데이터를 포함하여 행의 데이터에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="5da54-111">로드 메서드</span><span class="sxs-lookup"><span data-stu-id="5da54-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="5da54-112">사용 방법을 설명 합니다는 **부하** 메서드에서 채울를 **DataTable** 행.</span><span class="sxs-lookup"><span data-stu-id="5da54-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="5da54-113">DataTable 편집</span><span class="sxs-lookup"><span data-stu-id="5da54-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="5da54-114">제안된 변경을 확인하여 승인할 때까지 행 변경을 일시 중단하는 작업을 포함하여, 행의 데이터를 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="5da54-115">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="5da54-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="5da54-116">행의 여러 상태에 관한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="5da54-117">DataRow 삭제</span><span class="sxs-lookup"><span data-stu-id="5da54-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="5da54-118">테이블에서 행을 삭제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="5da54-119">행 오류 정보</span><span class="sxs-lookup"><span data-stu-id="5da54-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="5da54-120">응용 프로그램 내의 데이터에서 발생하는 문제의 해결에 유용하도록 행마다 오류 정보를 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="5da54-121">AcceptChanges 및 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="5da54-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="5da54-122">행의 변경된 내용을 승인하거나 거부하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5da54-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da54-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="5da54-123">See also</span></span>

- [<span data-ttu-id="5da54-124">DataTable</span><span class="sxs-lookup"><span data-stu-id="5da54-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="5da54-125">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="5da54-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="5da54-126">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5da54-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
