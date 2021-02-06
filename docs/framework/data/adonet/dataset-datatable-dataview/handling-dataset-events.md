---
description: '자세한 정보: 데이터 집합 이벤트 처리'
title: 데이터 세트 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: a0000396c7c1e2762a5a2937f7979d917257facc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652369"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="29612-103">데이터 세트 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="29612-103">Handling DataSet Events</span></span>

<span data-ttu-id="29612-104"><xref:System.Data.DataSet> 개체는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>및 <xref:System.Data.DataSet.MergeFailed>의 세 가지 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-104">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="29612-105">MergeFailed 이벤트</span><span class="sxs-lookup"><span data-stu-id="29612-105">The MergeFailed Event</span></span>  

 <span data-ttu-id="29612-106">`DataSet` 개체의 이벤트 중 가장 많이 사용되는 `MergeFailed`이벤트는 병합하는 `DataSet` 개체의 스키마에서 충돌이 발생할 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="29612-106">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="29612-107">이러한 충돌은 대상 및 소스 <xref:System.Data.DataRow> 의 기본 키 값이 동일하고 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성이 `true`로 설정된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-107">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="29612-108">예를 들어 병합할 테이블의 기본 키 열이 두 `DataSet` 개체에 있는 테이블 간에서 서로 같으면 예외가 throw되고 `MergeFailed` 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-108">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="29612-109"><xref:System.Data.MergeFailedEventArgs> 이벤트로 전달되는 `MergeFailed` 개체에는 두 <xref:System.Data.MergeFailedEventArgs.Conflict%2A> 개체 사이의 스키마에서 발생한 충돌을 식별하는 `DataSet` 속성과 충돌한 테이블 이름을 식별하는 <xref:System.Data.MergeFailedEventArgs.Table%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29612-109">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="29612-110">다음 코드 단편에서는 `MergeFailed` 이벤트에 대한 이벤트 처리기를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29612-110">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="29612-111">Initialized 이벤트</span><span class="sxs-lookup"><span data-stu-id="29612-111">The Initialized Event</span></span>  

 <span data-ttu-id="29612-112"><xref:System.Data.DataSet.Initialized> 이벤트는 `DataSet` 생성자가 `DataSet`의 새 인스턴스를 초기화한 후 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-112">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="29612-113"><xref:System.Data.DataSet.IsInitialized%2A> 이 초기화를 완료하면 `true` 속성이 `DataSet` 를 반환하고, 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-113">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="29612-114"><xref:System.Data.DataSet.BeginInit%2A> 의 초기화를 시작하는 `DataSet`메서드는 <xref:System.Data.DataSet.IsInitialized%2A> 를 `false`로 설정하고,</span><span class="sxs-lookup"><span data-stu-id="29612-114">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="29612-115"><xref:System.Data.DataSet.EndInit%2A> 의 초기화를 끝내는 `DataSet`메서드는 이를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-115">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="29612-116">이러한 메서드는 Visual Studio 디자인 환경에서 다른 구성 요소에 사용 되는를 초기화 하는 데 사용 됩니다 `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="29612-116">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="29612-117">사용자 코드에는 일반적으로 이러한 메서드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29612-117">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="29612-118">Disposed 이벤트</span><span class="sxs-lookup"><span data-stu-id="29612-118">The Disposed Event</span></span>  

 <span data-ttu-id="29612-119">`DataSet` 은 <xref:System.ComponentModel.MarshalByValueComponent> 메서드와 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 이벤트를 모두 노출하는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="29612-119">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="29612-120"><xref:System.ComponentModel.MarshalByValueComponent.Disposed>이벤트는 구성 요소에서 삭제 된 이벤트를 수신 하는 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-120">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="29612-121"><xref:System.ComponentModel.MarshalByValueComponent.Disposed> `DataSet` 메서드가 호출 될 때 코드를 실행 하려는 경우의 이벤트를 사용할 수 있습니다 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> .</span><span class="sxs-lookup"><span data-stu-id="29612-121">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="29612-122"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 에서 사용 하는 리소스를 해제 <xref:System.ComponentModel.MarshalByValueComponent> 합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-122"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29612-123">`DataSet`및 `DataTable` 개체는에서 상속 <xref:System.ComponentModel.MarshalByValueComponent> 되며 <xref:System.Runtime.Serialization.ISerializable> 원격을 위해 인터페이스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29612-123">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="29612-124">이 두 개체는 원격으로 연결할 수 있는 유일한 ADO.NET 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29612-124">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="29612-125">자세한 내용은 [.Net Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29612-125">For more information, see [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="29612-126">로 작업할 때 사용할 수 있는 다른 이벤트에 대 한 자세한 내용은 `DataSet` [DataTable 이벤트 처리](handling-datatable-events.md) 및 [DataAdapter 이벤트 처리](../handling-dataadapter-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29612-126">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](handling-datatable-events.md) and [Handling DataAdapter Events](../handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29612-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29612-127">See also</span></span>

- [<span data-ttu-id="29612-128">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="29612-128">DataSets, DataTables, and DataViews</span></span>](index.md)
- <span data-ttu-id="29612-129">[데이터 유효성 검사](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="29612-129">[Validating Data](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="29612-130">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="29612-130">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="29612-131">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="29612-131">ADO.NET Overview</span></span>](../ado-net-overview.md)
