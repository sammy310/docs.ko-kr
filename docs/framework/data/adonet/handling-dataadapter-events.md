---
description: '자세한 정보: DataAdapter 이벤트 처리'
title: DataAdapter 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: 045a48ae545ad4354844dd451ff58618b760a9a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723948"
---
# <a name="handling-dataadapter-events"></a><span data-ttu-id="5598c-103">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="5598c-103">Handling DataAdapter Events</span></span>

<span data-ttu-id="5598c-104">ADO.NET <xref:System.Data.Common.DataAdapter>는 데이터 소스의 데이터가 변경되었을 때 응답하는 데 사용할 수 있는 세 가지 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-104">The ADO.NET <xref:System.Data.Common.DataAdapter> exposes three events that you can use to respond to changes made to data at the data source.</span></span> <span data-ttu-id="5598c-105">다음 표에서는 `DataAdapter` 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-105">The following table shows the `DataAdapter` events.</span></span>  
  
|<span data-ttu-id="5598c-106">이벤트</span><span class="sxs-lookup"><span data-stu-id="5598c-106">Event</span></span>|<span data-ttu-id="5598c-107">Description</span><span class="sxs-lookup"><span data-stu-id="5598c-107">Description</span></span>|  
|-----------|-----------------|  
|`RowUpdating`|<span data-ttu-id="5598c-108">`Update` 메서드 중 하나를 호출하여 행에 대해 UPDATE, INSERT 또는 DELETE 작업을 시작하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-108">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is about to begin.</span></span>|  
|`RowUpdated`|<span data-ttu-id="5598c-109">`Update` 메서드 중 하나를 호출하여 행에 대한 UPDATE, INSERT 또는 DELETE 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-109">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is complete.</span></span>|  
|`FillError`|<span data-ttu-id="5598c-110">`Fill` 작업 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-110">An error has occurred during a `Fill` operation.</span></span>|  
  
## <a name="rowupdating-and-rowupdated"></a><span data-ttu-id="5598c-111">RowUpdating 및 RowUpdated</span><span class="sxs-lookup"><span data-stu-id="5598c-111">RowUpdating and RowUpdated</span></span>  

 <span data-ttu-id="5598c-112">`RowUpdating`은 <xref:System.Data.DataSet>의 행 업데이트가 데이터 소스에서 처리되기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-112">`RowUpdating` is raised before any update to a row from the <xref:System.Data.DataSet> has been processed at the data source.</span></span> <span data-ttu-id="5598c-113">`RowUpdated`는 `DataSet`의 행 업데이트가 데이터 소스에서 처리된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-113">`RowUpdated` is raised after any update to a row from the `DataSet` has been processed at the data source.</span></span> <span data-ttu-id="5598c-114">결과적으로 `RowUpdating`을 사용하면 업데이트가 발생하기 전에 업데이트 동작을 수정하거나, 업데이트가 발생할 경우 추가 처리 방법을 제공하거나, 업데이트된 행에 대한 참조를 유지하거나, 현재 업데이트를 취소하고 일괄 프로세스로 나중에 처리하도록 예약하는 것과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-114">As a result, you can use `RowUpdating` to modify update behavior before it happens, to provide additional handling when an update will occur, to retain a reference to an updated row, to cancel the current update and schedule it for a batch process to be processed later, and so on.</span></span> <span data-ttu-id="5598c-115">`RowUpdated`는 업데이트 중에 발생하는 오류와 예외에 응답하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-115">`RowUpdated` is useful for responding to errors and exceptions that occur during the update.</span></span> <span data-ttu-id="5598c-116">재시도 논리 등은 물론이고 오류 정보도 에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-116">You can add error information to the `DataSet`, as well as retry logic, and so on.</span></span>  
  
 <span data-ttu-id="5598c-117"><xref:System.Data.Common.RowUpdatingEventArgs> 및 <xref:System.Data.Common.RowUpdatedEventArgs> 이벤트로 전달되는 `RowUpdating` 및 `RowUpdated` 인수에는 업데이트를 수행하는 데 사용되는 `Command` 개체를 참조하는 `Command` 속성, 업데이트된 정보가 포함된 `Row` 개체를 참조하는 `DataRow` 속성, 수행되는 업데이트 형식을 나타내는 `StatementType` 속성, `TableMapping` 속성(해당되는 경우) 및 작업의 `Status` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-117">The <xref:System.Data.Common.RowUpdatingEventArgs> and <xref:System.Data.Common.RowUpdatedEventArgs> arguments passed to the `RowUpdating` and `RowUpdated` events include the following: a `Command` property that references the `Command` object being used to perform the update; a `Row` property that references the `DataRow` object containing the updated information; a `StatementType` property for what type of update is being performed; the `TableMapping`, if applicable; and the `Status` of the operation.</span></span>  
  
 <span data-ttu-id="5598c-118"> 속성을 사용하면 작업 중에 오류가 발생했는지 확인하여 필요할 경우 현재 행 및 결과 행에 대한 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-118">You can use the `Status` property to determine if an error has occurred during the operation and, if desired, to control the actions against the current and resulting rows.</span></span> <span data-ttu-id="5598c-119">이벤트가 발생할 때 `Status` 속성은 `Continue` 또는 `ErrorsOccurred`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-119">When the event occurs, the `Status` property equals either `Continue` or `ErrorsOccurred`.</span></span> <span data-ttu-id="5598c-120">다음 표에서는 업데이트하는 동안 후속 동작을 제어하기 위해 설정할 수 있는  속성 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-120">The following table shows the values to which you can set the `Status` property in order to control later actions during the update.</span></span>  
  
|<span data-ttu-id="5598c-121">상태</span><span class="sxs-lookup"><span data-stu-id="5598c-121">Status</span></span>|<span data-ttu-id="5598c-122">Description</span><span class="sxs-lookup"><span data-stu-id="5598c-122">Description</span></span>|  
|------------|-----------------|  
|`Continue`|<span data-ttu-id="5598c-123">업데이트 작업을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-123">Continue the update operation.</span></span>|  
|`ErrorsOccurred`|<span data-ttu-id="5598c-124">업데이트 작업을 중단하고 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-124">Abort the update operation and throw an exception.</span></span>|  
|`SkipCurrentRow`|<span data-ttu-id="5598c-125">현재 행을 무시하고 업데이트 작업을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-125">Ignore the current row and continue the update operation.</span></span>|  
|`SkipAllRemainingRows`|<span data-ttu-id="5598c-126">업데이트 작업을 중단하지만 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-126">Abort the update operation but do not throw an exception.</span></span>|  
  
 <span data-ttu-id="5598c-127">`Status` 속성을 `ErrorsOccurred`로 설정하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-127">Setting the `Status` property to `ErrorsOccurred` causes an exception to be thrown.</span></span> <span data-ttu-id="5598c-128">`Errors` 속성을 설정하면 원하는 예외를 throw하도록 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-128">You can control which exception is thrown by setting the `Errors` property to the desired exception.</span></span> <span data-ttu-id="5598c-129">`Status`에 대해 다른 값 중 하나를 사용하면 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-129">Using one of the other values for `Status` prevents an exception from being thrown.</span></span>  
  
 <span data-ttu-id="5598c-130">또한  속성을 사용하여 업데이트된 행의 오류를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-130">You can also use the `ContinueUpdateOnError` property to handle errors for updated rows.</span></span> <span data-ttu-id="5598c-131">`DataAdapter.ContinueUpdateOnError`가 `true`인 경우 행을 업데이트한 결과로 예외가 throw되면 예외 텍스트가 특정 행의 `RowError` 정보에 배치되고 예외가 throw되지 않은 상태에서 계속 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-131">If `DataAdapter.ContinueUpdateOnError` is `true`, when an update to a row results in an exception being thrown, the text of the exception is placed into the `RowError` information of the particular row, and processing continues without throwing an exception.</span></span> <span data-ttu-id="5598c-132">이렇게 하면 오류 발생 시 이에 응답할 수 있도록 하는 와는 달리, 가 완료될 때 오류에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-132">This enables you to respond to errors when the `Update` is complete, in contrast to the `RowUpdated` event, which enables you to respond to errors when the error is encountered.</span></span>  
  
 <span data-ttu-id="5598c-133">다음 코드 샘플에서는 이벤트 처리기를 추가 및 제거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-133">The following code sample shows how to both add and remove event handlers.</span></span> <span data-ttu-id="5598c-134"> 이벤트 처리기는 타임스탬프를 사용하여 삭제된 모든 레코드의 로그를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-134">The `RowUpdating` event handler writes a log of all deleted records with a time stamp.</span></span> <span data-ttu-id="5598c-135">`RowUpdated` 이벤트 처리기는 `DataSet`의 행에 대한 `RowError` 속성에 오류 정보를 추가하고 예외를 표시하지 않으며 처리(`ContinueUpdateOnError` = `true`의 동작을 미러링)를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-135">The `RowUpdated` event handler adds error information to the `RowError` property of the row in the `DataSet`, suppresses the exception, and continues processing (mirroring the behavior of `ContinueUpdateOnError` = `true`).</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
' Add handlers.  
AddHandler custAdapter.RowUpdating, New SqlRowUpdatingEventHandler( _  
  AddressOf OnRowUpdating)  
AddHandler custAdapter.RowUpdated, New SqlRowUpdatedEventHandler(  
  AddressOf OnRowUpdated)  
  
' Set DataAdapter command properties, fill DataSet, and modify DataSet.  
  
custAdapter.Update(custDS, "Customers")  
  
' Remove handlers.  
RemoveHandler custAdapter.RowUpdating, _  
  New SqlRowUpdatingEventHandler(AddressOf OnRowUpdating)  
RemoveHandler custAdapter.RowUpdated, _  
  New SqlRowUpdatedEventHandler(AddressOf OnRowUpdated)  
  
Private Shared Sub OnRowUpdating(sender As Object, _  
  args As SqlRowUpdatingEventArgs)  
  If args.StatementType = StatementType.Delete Then  
    Dim tw As System.IO.TextWriter = _  
  System.IO.File.AppendText("Deletes.log")  
    tw.WriteLine( _  
      "{0}: Customer {1} Deleted.", DateTime.Now, args.Row(_  
      "CustomerID", DataRowVersion.Original))  
    tw.Close()  
  End If  
End Sub  
  
Private Shared Sub OnRowUpdated( _  
  sender As Object, args As SqlRowUpdatedEventArgs)  
  If args.Status = UpdateStatus.ErrorsOccurred  
    args.Status = UpdateStatus.SkipCurrentRow  
    args.Row.RowError = args.Errors.Message  
  End If  
End Sub  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
// Add handlers.  
custAdapter.RowUpdating += new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
// Set DataAdapter command properties, fill DataSet, modify DataSet.  
  
custAdapter.Update(custDS, "Customers");  
  
// Remove handlers.  
custAdapter.RowUpdating -= new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated -= new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
protected static void OnRowUpdating(  
  object sender, SqlRowUpdatingEventArgs args)  
{  
  if (args.StatementType == StatementType.Delete)  
  {  
    System.IO.TextWriter tw = System.IO.File.AppendText("Deletes.log");  
    tw.WriteLine(  
      "{0}: Customer {1} Deleted.", DateTime.Now,
       args.Row["CustomerID", DataRowVersion.Original]);  
    tw.Close();  
  }  
}  
  
protected static void OnRowUpdated(  
  object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.Status == UpdateStatus.ErrorsOccurred)  
  {  
    args.Row.RowError = args.Errors.Message;  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="fillerror"></a><span data-ttu-id="5598c-136">FillError</span><span class="sxs-lookup"><span data-stu-id="5598c-136">FillError</span></span>  

 <span data-ttu-id="5598c-137">는  작업 중에 오류가 발생하면  이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-137">The `DataAdapter` issues the `FillError` event when an error occurs during a `Fill` operation.</span></span> <span data-ttu-id="5598c-138">이런 형식의 오류는 추가 중인 행의 데이터를 정밀도의 손실 없이 .NET Framework 형식으로 변환할 수 없을 때 흔히 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-138">This type of error commonly occurs when the data in the row being added could not be converted to a .NET Framework type without some loss of precision.</span></span>  
  
 <span data-ttu-id="5598c-139"> 작업 중에 오류가 발생하면 현재 행이 에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-139">If an error occurs during a `Fill` operation, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="5598c-140"> 이벤트를 사용하여 오류를 해결하고 행을 추가하거나, 제외된 행을 무시하고  작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-140">The `FillError` event enables you to resolve the error and add the row, or to ignore the excluded row and continue the `Fill` operation.</span></span>  
  
 <span data-ttu-id="5598c-141"> 이벤트에 전달된 에는 오류에 응답하고 오류를 해결할 수 있는 몇 가지 속성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-141">The `FillErrorEventArgs` passed to the `FillError` event can contain several properties that enable you to respond to and resolve errors.</span></span> <span data-ttu-id="5598c-142">다음 표에서는  개체의 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-142">The following table shows the properties of the `FillErrorEventArgs` object.</span></span>  
  
|<span data-ttu-id="5598c-143">속성</span><span class="sxs-lookup"><span data-stu-id="5598c-143">Property</span></span>|<span data-ttu-id="5598c-144">Description</span><span class="sxs-lookup"><span data-stu-id="5598c-144">Description</span></span>|  
|--------------|-----------------|  
|`Errors`|<span data-ttu-id="5598c-145">발생한 `Exception`입니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-145">The `Exception` that occurred.</span></span>|  
|`DataTable`|<span data-ttu-id="5598c-146">오류가 발생했을 때 채워지고 있던 `DataTable` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-146">The `DataTable` object being filled when the error occurred.</span></span>|  
|`Values`|<span data-ttu-id="5598c-147">오류가 발생했을 때 추가되고 있던 행의 값을 포함하는 개체 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-147">An array of objects that contains the values of the row being added when the error occurred.</span></span> <span data-ttu-id="5598c-148"> 배열의 서수 참조는 추가되고 있던 행의 열에 대한 서수 참조에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-148">The ordinal references of the `Values` array correspond to the ordinal references of the columns of the row being added.</span></span> <span data-ttu-id="5598c-149">예를 들어, 은 행의 첫째 열로 추가되고 있던 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-149">For example, `Values[0]` is the value that was being added as the first column of the row.</span></span>|  
|`Continue`|<span data-ttu-id="5598c-150">예외를 throw할 것인지 여부를 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-150">Allows you to choose whether or not to throw an exception.</span></span> <span data-ttu-id="5598c-151"> 속성을 로 설정하면 현재  작업이 중단되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-151">Setting the `Continue` property to `false` will halt the current `Fill` operation, and an exception will be thrown.</span></span> <span data-ttu-id="5598c-152">`Continue`를 `true`로 설정하면 오류가 발생하더라도 `Fill` 작업이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-152">Setting `Continue` to `true` continues the `Fill` operation despite the error.</span></span>|  
  
 <span data-ttu-id="5598c-153">다음 코드 예제에서는 `FillError`의 `DataAdapter` 이벤트에 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-153">The following code example adds an event handler for the `FillError` event of the `DataAdapter`.</span></span> <span data-ttu-id="5598c-154">이 예제에서는  이벤트 코드에서 정밀도가 손실될 가능성이 있는지 확인하여 예외에 응답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5598c-154">In the `FillError` event code, the example determines if there is the potential for precision loss, providing the opportunity to respond to the exception.</span></span>  
  
```vb  
AddHandler adapter.FillError, New FillErrorEventHandler( _  
  AddressOf FillError)  
  
Dim dataSet As DataSet = New DataSet  
adapter.Fill(dataSet, "ThisTable")  
  
Private Shared Sub FillError(sender As Object, _  
  args As FillErrorEventArgs)  
  If args.Errors.GetType() Is Type.GetType("System.OverflowException") Then  
    ' Code to handle precision loss.  
    ' Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(New Object() _  
      {args.Values(0), args.Values(1), DBNull.Value})  
    ' Set the RowError containing the value for the third column.  
    myRow.RowError = _  
      "OverflowException encountered. Value from data source: " & _  
      args.Values(2)  
    args.Continue = True  
  End If  
End Sub  
```  
  
```csharp  
adapter.FillError += new FillErrorEventHandler(FillError);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "ThisTable");  
  
protected static void FillError(object sender, FillErrorEventArgs args)  
{  
  if (args.Errors.GetType() == typeof(System.OverflowException))  
  {  
    // Code to handle precision loss.  
    //Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(new object[]  
       {args.Values[0], args.Values[1], DBNull.Value});  
    //Set the RowError containing the value for the third column.  
    myRow.RowError =
       "OverflowException Encountered. Value from data source: " +  
       args.Values[2];  
    args.Continue = true;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5598c-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5598c-155">See also</span></span>

- [<span data-ttu-id="5598c-156">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="5598c-156">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="5598c-157">데이터 세트 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="5598c-157">Handling DataSet Events</span></span>](./dataset-datatable-dataview/handling-dataset-events.md)
- [<span data-ttu-id="5598c-158">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="5598c-158">Handling DataTable Events</span></span>](./dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="5598c-159">이벤트</span><span class="sxs-lookup"><span data-stu-id="5598c-159">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="5598c-160">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="5598c-160">ADO.NET Overview</span></span>](ado-net-overview.md)
