---
title: DataAdapters로 데이터 원본 업데이트
description: DataAdapter의 업데이트 메서드가 데이터 집합의 변경 내용을 ADO.NET 응용 프로그램의 데이터 원본으로 다시 확인 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: e2348a3a89aa1c28856bfc21aaa25f2c8327aac7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286186"
---
# <a name="updating-data-sources-with-dataadapters"></a><span data-ttu-id="bfad4-103">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="bfad4-103">Updating Data Sources with DataAdapters</span></span>

<span data-ttu-id="bfad4-104">`Update`의 <xref:System.Data.Common.DataAdapter> 메서드를 호출하면 <xref:System.Data.DataSet>의 변경 내용이 데이터 소스에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-104">The `Update` method of the <xref:System.Data.Common.DataAdapter> is called to resolve changes from a <xref:System.Data.DataSet> back to the data source.</span></span> <span data-ttu-id="bfad4-105">`Update` 메서드는 `Fill` 메서드와 마찬가지로 `DataSet`의 인스턴스, 선택적 <xref:System.Data.DataTable> 개체 또는 `DataTable` 이름을 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-105">The `Update` method, like the `Fill` method, takes as arguments an instance of a `DataSet`, and an optional <xref:System.Data.DataTable> object or `DataTable` name.</span></span> <span data-ttu-id="bfad4-106">`DataSet` 인스턴스는 변경 내용을 포함하는 `DataSet`이며 `DataTable`은 변경 내용을 검색할 테이블을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-106">The `DataSet` instance is the `DataSet` that contains the changes that have been made, and the `DataTable` identifies the table from which to retrieve the changes.</span></span> <span data-ttu-id="bfad4-107">`DataTable`을 지정하지 않으면 `DataTable`의 첫 번째 `DataSet`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-107">If no `DataTable` is specified, the first `DataTable` in the `DataSet` is used.</span></span>

<span data-ttu-id="bfad4-108">`Update` 메서드를 호출하면 `DataAdapter`가 변경 내용을 분석하여 INSERT, UPDATE, DELETE 등의 적절한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-108">When you call the `Update` method, the `DataAdapter` analyzes the changes that have been made and executes the appropriate command (INSERT, UPDATE, or DELETE).</span></span> <span data-ttu-id="bfad4-109">`DataAdapter`에 대한 변경 사항이 발견되면 <xref:System.Data.DataRow>는 <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 또는 <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>를 사용하여 변경 내용을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-109">When the `DataAdapter` encounters a change to a <xref:System.Data.DataRow>, it uses the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, or <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> to process the change.</span></span> <span data-ttu-id="bfad4-110">이로써 가능한 경우 디자인 타임에 저장 프로시저를 사용하여 명령 구문을 지정함으로써 ADO.NET 애플리케이션의 성능을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-110">This allows you to maximize the performance of your ADO.NET application by specifying command syntax at design time and, where possible, through the use of stored procedures.</span></span> <span data-ttu-id="bfad4-111">`Update`를 호출하기 전에 명령을 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-111">You must explicitly set the commands before calling `Update`.</span></span> <span data-ttu-id="bfad4-112">`Update`를 호출했는데 삭제된 행에 대한 `DeleteCommand`가 없는 경우와 같이 특정 업데이트에 사용할 적절한 명령이 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-112">If `Update` is called and the appropriate command does not exist for a particular update (for example, no `DeleteCommand` for deleted rows), an exception is thrown.</span></span>

> [!NOTE]
> <span data-ttu-id="bfad4-113">SQL Server 저장 프로시저를 사용 하 여를 사용 하 여 데이터를 편집 하거나 삭제 하는 경우 `DataAdapter` 저장 프로시저 정의에 SET NOCOUNT ON을 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-113">If you are using SQL Server stored procedures to edit or delete data using a `DataAdapter`, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="bfad4-114">이로 인해 영향을 받는 행 수가 0으로 반환 되어가 `DataAdapter` 동시성 충돌로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-114">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="bfad4-115">이 경우이 throw 됩니다 <xref:System.Data.DBConcurrencyException> .</span><span class="sxs-lookup"><span data-stu-id="bfad4-115">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>

<span data-ttu-id="bfad4-116">명령 매개 변수를 사용하여 `DataSet`의 수정된 각 행에 대해 SQL 문이나 저장 프로시저의 입력 및 출력 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-116">Command parameters can be used to specify input and output values for an SQL statement or stored procedure for each modified row in a `DataSet`.</span></span> <span data-ttu-id="bfad4-117">자세한 내용은 [DataAdapter 매개 변수](dataadapter-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfad4-117">For more information, see [DataAdapter Parameters](dataadapter-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bfad4-118"><xref:System.Data.DataTable>에서의 행 삭제 및 제거의 차이점을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-118">It is important to understand the difference between deleting a row in a <xref:System.Data.DataTable> and removing the row.</span></span> <span data-ttu-id="bfad4-119">`Remove` 또는 `RemoveAt` 메서드를 호출하면 행이 즉시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-119">When you call the `Remove` or `RemoveAt` method, the row is removed immediately.</span></span> <span data-ttu-id="bfad4-120">그런 다음 `DataTable`에 `DataSet` 또는 `DataAdapter`을 전달하고 `Update`를 호출하면 백 엔드 데이터 소스에 있는 해당 행은 아무런 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-120">Any corresponding rows in the back end data source will not be affected if you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`.</span></span> <span data-ttu-id="bfad4-121">`Delete` 메서드를 사용하면 행이 `DataTable`에 그대로 남아 있고 삭제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-121">When you use the `Delete` method, the row remains in the `DataTable` and is marked for deletion.</span></span> <span data-ttu-id="bfad4-122">그런 다음 `DataTable`에 `DataSet` 또는 `DataAdapter`을 전달하고 `Update`를 호출하면 백 엔드 데이터 소스의 해당 행이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-122">If you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`, the corresponding row in the back end data source is deleted.</span></span>

<span data-ttu-id="bfad4-123">`DataTable`이 단일 데이터베이스 테이블에 매핑되거나 단일 데이터베이스 테이블에서 생성된 경우에는 <xref:System.Data.Common.DbCommandBuilder> 개체를 사용하여 `DeleteCommand`의 `InsertCommand`, `UpdateCommand` 및 `DataAdapter` 개체를 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-123">If your `DataTable` maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` objects for the `DataAdapter`.</span></span> <span data-ttu-id="bfad4-124">자세한 내용은 [CommandBuilders를 사용 하 여 명령 생성](generating-commands-with-commandbuilders.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfad4-124">For more information, see [Generating Commands with CommandBuilders](generating-commands-with-commandbuilders.md).</span></span>

## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a><span data-ttu-id="bfad4-125">UpdatedRowSource를 사용하여 DataSet에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="bfad4-125">Using UpdatedRowSource to Map Values to a DataSet</span></span>

<span data-ttu-id="bfad4-126">`DataTable` 개체의 `DataAdapter` 속성을 사용하면 <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A>의 Update 메서드를 호출한 이후 데이터 소스에서 반환된 값이 <xref:System.Data.Common.DbCommand>에 다시 매핑되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-126">You can control how the values returned from the data source are mapped back to the `DataTable` following a call to the Update method of a `DataAdapter`, by using the <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> property of a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="bfad4-127">`UpdatedRowSource` 속성을 <xref:System.Data.UpdateRowSource> 열거형 값 중 하나로 설정하면 `DataAdapter` 명령에서 반환하는 출력 매개 변수를 무시할지 아니면 `DataSet`의 변경된 행에 적용할지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-127">By setting the `UpdatedRowSource` property to one of the <xref:System.Data.UpdateRowSource> enumeration values, you can control whether output parameters returned by the `DataAdapter` commands are ignored or applied to the changed row in the `DataSet`.</span></span> <span data-ttu-id="bfad4-128">반환되는 첫 번째 행이 있는 경우 이를 `DataTable`의 변경된 행에 적용할지 여부도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-128">You can also specify whether the first returned row (if it exists) is applied to the changed row in the `DataTable`.</span></span>

<span data-ttu-id="bfad4-129">다음 표에서는 `UpdateRowSource` 열거형의 여러 값과 각 값이 `DataAdapter`에 사용하는 명령의 동작에 미치는 영향에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-129">The following table describes the different values of the `UpdateRowSource` enumeration and how they affect the behavior of a command used with a `DataAdapter`.</span></span>

|<span data-ttu-id="bfad4-130">UpdatedRowSource 열거형</span><span class="sxs-lookup"><span data-stu-id="bfad4-130">UpdatedRowSource Enumeration</span></span>|<span data-ttu-id="bfad4-131">Description</span><span class="sxs-lookup"><span data-stu-id="bfad4-131">Description</span></span>|
|----------------------------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|<span data-ttu-id="bfad4-132">출력 매개 변수 및 반환된 결과 집합의 첫 번째 행 모두 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-132">Both the output parameters and the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|<span data-ttu-id="bfad4-133">반환된 결과 집합의 첫 번째 행 데이터만 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-133">Only the data in the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.None>|<span data-ttu-id="bfad4-134">출력 매개 변수 또는 반환된 결과 집합의 행이 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-134">Any output parameters or rows of a returned result set are ignored.</span></span>|
|<xref:System.Data.UpdateRowSource.OutputParameters>|<span data-ttu-id="bfad4-135">출력 매개 변수만 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-135">Only output parameters may be mapped to the changed row in the `DataSet`.</span></span>|

<span data-ttu-id="bfad4-136">`Update` 메서드는 변경 내용을 데이터 소스에 다시 적용하지만 사용자가 `DataSet`을 마지막으로 채운 이후에 다른 클라이언트에서 데이터 소스의 데이터를 수정했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-136">The `Update` method resolves your changes back to the data source; however other clients may have modified data at the data source since the last time you filled the `DataSet`.</span></span> <span data-ttu-id="bfad4-137">현재 데이터로 `DataSet`을 새로 고치려면 `DataAdapter` 및 `Fill` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-137">To refresh your `DataSet` with current data, use the `DataAdapter` and `Fill` method.</span></span> <span data-ttu-id="bfad4-138">그러면 새 행이 테이블에 추가되고 업데이트된 정보가 기존 행에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-138">New rows will be added to the table, and updated information will be incorporated into existing rows.</span></span> <span data-ttu-id="bfad4-139">`Fill` 메서드는 `DataSet`에 있는 행과 `SelectCommand`에서 반환된 행의 기본 키 값을 검사하여 새 행을 추가할지 또는 기존 행을 업데이트할지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-139">The `Fill` method determines whether a new row will be added or an existing row will be updated by examining the primary key values of the rows in the `DataSet` and the rows returned by the `SelectCommand`.</span></span> <span data-ttu-id="bfad4-140">`Fill`가 반환한 결과 행의 기본 키 값과 일치하는 `DataSet` 행의 기본 키 값이 발견되면 `SelectCommand` 메서드는 기존 행을 `SelectCommand`가 반환한 행의 정보로 업데이트하고 기존 행의 <xref:System.Data.DataRow.RowState%2A>를 `Unchanged`로 설정합니다</span><span class="sxs-lookup"><span data-stu-id="bfad4-140">If the `Fill` method encounters a primary key value for a row in the `DataSet` that matches a primary key value from a row in the results returned by the `SelectCommand`, it updates the existing row with the information from the row returned by the `SelectCommand` and sets the <xref:System.Data.DataRow.RowState%2A> of the existing row to `Unchanged`.</span></span> <span data-ttu-id="bfad4-141">`SelectCommand`가 반환한 행의 기본 키 값이 `DataSet` 행의 기본 키 값과 일치하지 않으면 `Fill` 메서드는 `RowState`가 `Unchanged`인 새 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-141">If a row returned by the `SelectCommand` has a primary key value that does not match any of the primary key values of the rows in the `DataSet`, the `Fill` method adds a new row with a `RowState` of `Unchanged`.</span></span>

> [!NOTE]
> <span data-ttu-id="bfad4-142">`SelectCommand`가 OUTER JOIN의 결과를 반환하면 `DataAdapter`는 결과 `PrimaryKey`에 대해 `DataTable` 값을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-142">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` will not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="bfad4-143">행 중복 문제를 해결하려면 `PrimaryKey`를 직접 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-143">You must define the `PrimaryKey` yourself to ensure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="bfad4-144">자세한 내용은 [기본 키 정의](./dataset-datatable-dataview/defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-144">For more information, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>

<span data-ttu-id="bfad4-145">메서드를 호출할 때 발생할 수 있는 예외를 처리 하려면 이벤트를 사용 하 여 `Update` `RowUpdated` 발생 한 행 업데이트 오류에 대응 하거나 ( [DataAdapter 이벤트 처리](handling-dataadapter-events.md)참조) `DataAdapter.ContinueUpdateOnError` ,를 `true` 호출 하기 전에를로 설정 하 `Update` 고 `RowError` 업데이트가 완료 되 면 특정 행의 속성에 저장 된 오류 정보에 응답 합니다 ( [행 오류 정보](./dataset-datatable-dataview/row-error-information.md)참조).</span><span class="sxs-lookup"><span data-stu-id="bfad4-145">To handle exceptions that may occur when calling the `Update` method, you can use the `RowUpdated` event to respond to row update errors as they occur (see [Handling DataAdapter Events](handling-dataadapter-events.md)), or you can set `DataAdapter.ContinueUpdateOnError` to `true` before calling `Update`, and respond to the error information stored in the `RowError` property of a particular row when the update is complete (see [Row Error Information](./dataset-datatable-dataview/row-error-information.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="bfad4-146">, 또는에서를 호출 하면의 `AcceptChanges` `DataSet` `DataTable` `DataRow` 모든 값이에 `Original` `DataRow` `Current` 대 한 값으로 덮어쓰여집니다 `DataRow` .</span><span class="sxs-lookup"><span data-stu-id="bfad4-146">Calling `AcceptChanges` on the `DataSet`, `DataTable`, or `DataRow` will cause all `Original` values for a `DataRow` to be overwritten with the `Current` values for the `DataRow`.</span></span> <span data-ttu-id="bfad4-147">행을 고유하게 식별하는 필드 값을 수정한 경우 `AcceptChanges`를 호출하면 `Original` 값이 데이터 소스의 값과 더 이상 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-147">If the field values that identify the row as unique have been modified, after calling `AcceptChanges` the `Original` values will no longer match the values in the data source.</span></span> <span data-ttu-id="bfad4-148">`AcceptChanges`는 `DataAdapter`의 Update 메서드를 호출하는 동안 각 행에 대해 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-148">`AcceptChanges` is called automatically for each row during a call to the Update method of a `DataAdapter`.</span></span> <span data-ttu-id="bfad4-149">먼저 `AcceptChangesDuringUpdate`의 `DataAdapter` 속성을 false로 설정하거나 `RowUpdated` 이벤트에 대한 이벤트 처리기를 만들고 <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A>를 <xref:System.Data.UpdateStatus.SkipCurrentRow>로 설정하면 Update 메서드를 호출할 때 원래 값을 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-149">You can preserve the original values during a call to the Update method by first setting the `AcceptChangesDuringUpdate` property of the `DataAdapter` to false, or by creating an event handler for the `RowUpdated` event and setting the <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> to <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span></span> <span data-ttu-id="bfad4-150">자세한 내용은 [데이터 집합 콘텐츠 병합](./dataset-datatable-dataview/merging-dataset-contents.md) 및 [DataAdapter 이벤트 처리](handling-dataadapter-events.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfad4-150">For more information, see [Merging DataSet Contents](./dataset-datatable-dataview/merging-dataset-contents.md) and [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="bfad4-151">예제</span><span class="sxs-lookup"><span data-stu-id="bfad4-151">Example</span></span>

<span data-ttu-id="bfad4-152">다음 예제에서는의를 명시적으로 설정 하 `UpdateCommand` `DataAdapter` 고 해당 메서드를 호출 하 여 수정 된 행에 대 한 업데이트를 수행 하는 방법을 보여 줍니다 `Update` .</span><span class="sxs-lookup"><span data-stu-id="bfad4-152">The following examples demonstrate how to perform updates to modified rows by explicitly setting the `UpdateCommand` of a `DataAdapter` and calling its `Update` method.</span></span> <span data-ttu-id="bfad4-153">UPDATE 문의 WHERE 절에 지정된 매개 변수는 `Original`의 `SourceColumn` 값을 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-153">Notice that the parameter specified in the WHERE clause of the UPDATE statement is set to use the `Original` value of the `SourceColumn`.</span></span> <span data-ttu-id="bfad4-154">`Current` 값이 수정되어 데이터 소스에 있는 값과 일치하지 않을 수 있기 때문에 이 설정은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-154">This is important, because the `Current` value may have been modified and may not match the value in the data source.</span></span> <span data-ttu-id="bfad4-155">`Original` 값은 데이터 소스에서 `DataTable`을 채우는 데 사용한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-155">The `Original` value is the value that was used to populate the `DataTable` from the data source.</span></span>

[!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]

## <a name="autoincrement-columns"></a><span data-ttu-id="bfad4-156">AutoIncrement 열</span><span class="sxs-lookup"><span data-stu-id="bfad4-156">AutoIncrement Columns</span></span>

<span data-ttu-id="bfad4-157">데이터 소스의 테이블에 자동 증분 열이 있으면 저장 프로시저의 출력 매개 변수로 자동 증분 값을 반환하여 테이블의 열에 매핑하거나, 저장 프로시저 또는 SQL 문에서 반환된 결과 집합의 첫 번째 행에 있는 자동 증분 값을 반환하거나, `DataSet`의 `RowUpdated` 이벤트를 통해 추가적인 SELECT 문을 실행하여 `DataAdapter`의 열을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-157">If the tables from your data source have auto-incrementing columns, you can fill the columns in your `DataSet` either by returning the auto-increment value as an output parameter of a stored procedure and mapping that to a column in a table, by returning the auto-increment value in the first row of a result set returned by a stored procedure or SQL statement, or by using the `RowUpdated` event of the `DataAdapter` to execute an additional SELECT statement.</span></span> <span data-ttu-id="bfad4-158">자세한 내용 및 예제는 [id 또는 일련 번호 값 검색](retrieving-identity-or-autonumber-values.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfad4-158">For more information and an example, see [Retrieving Identity or Autonumber Values](retrieving-identity-or-autonumber-values.md).</span></span>

## <a name="ordering-of-inserts-updates-and-deletes"></a><span data-ttu-id="bfad4-159">삽입, 업데이트 및 삭제 순서</span><span class="sxs-lookup"><span data-stu-id="bfad4-159">Ordering of Inserts, Updates, and Deletes</span></span>

<span data-ttu-id="bfad4-160">대부분의 경우에는 `DataSet`을 통해 변경된 내용이 데이터 소스에 전송되는 순서가 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-160">In many circumstances, the order in which changes made through the `DataSet` are sent to the data source is important.</span></span> <span data-ttu-id="bfad4-161">예를 들어 기존 행의 기본 키 값을 업데이트하고 새 기본 키 값이 외래 키로 지정된 새 행을 추가하는 경우에는 삽입하기 전에 업데이트를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-161">For example, if a primary key value for an existing row is updated, and a new row has been added with the new primary key value as a foreign key, it is important to process the update before the insert.</span></span>

<span data-ttu-id="bfad4-162">`Select`의 `DataTable` 메서드를 사용하여 특정 `DataRow`의 행만 참조하는 `RowState` 배열을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-162">You can use the `Select` method of the `DataTable` to return a `DataRow` array that only references rows with a particular `RowState`.</span></span> <span data-ttu-id="bfad4-163">그런 다음 반환된 `DataRow` 배열을 `Update`의 `DataAdapter` 메서드에 전달하여 수정된 행을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-163">You can then pass the returned `DataRow` array to the `Update` method of the `DataAdapter` to process the modified rows.</span></span> <span data-ttu-id="bfad4-164">업데이트될 행의 하위 집합을 지정하여 삽입, 업데이트 및 삭제가 처리되는 순서를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-164">By specifying a subset of rows to be updated, you can control the order in which inserts, updates, and deletes are processed.</span></span>

## <a name="example"></a><span data-ttu-id="bfad4-165">예제</span><span class="sxs-lookup"><span data-stu-id="bfad4-165">Example</span></span>

<span data-ttu-id="bfad4-166">예를 들어, 다음 코드에서는 테이블의 삭제된 행이 먼저 처리되고 업데이트된 행과 삽입된 행이 차례로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-166">For example, the following code ensures that the deleted rows of the table are processed first, then the updated rows, and then the inserted rows.</span></span>

```vb
Dim table As DataTable = dataSet.Tables("Customers")

' First process deletes.
dataSet.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Deleted))

' Next process updates.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.ModifiedCurrent))

' Finally, process inserts.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Added))
```

```csharp
DataTable table = dataSet.Tables["Customers"];

// First process deletes.
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));

// Next process updates.
adapter.Update(table.Select(null, null,
  DataViewRowState.ModifiedCurrent));

// Finally, process inserts.
adapter.Update(table.Select(null, null, DataViewRowState.Added));
```

## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a><span data-ttu-id="bfad4-167">DataAdapter를 사용하여 데이터 검색 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="bfad4-167">Use a DataAdapter to Retrieve and Update Data</span></span>

<span data-ttu-id="bfad4-168">DataAdapter를 사용하여 데이터를 검색하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-168">You can use a DataAdapter to retrieve and update the data.</span></span>

- <span data-ttu-id="bfad4-169">이 샘플에서는 DataAdapter.AcceptChangesDuringFill을 사용하여 데이터베이스의 데이터를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-169">The sample uses DataAdapter.AcceptChangesDuringFill to clone the data in the database.</span></span> <span data-ttu-id="bfad4-170">이 속성이 false로 설정되어 있으면 테이블을 채울 때 AcceptChanges가 호출되지 않으며 새로 추가된 행은 삽입된 행으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-170">If the property is set as false, AcceptChanges is not called when filling the table, and the newly added rows are treated as inserted rows.</span></span> <span data-ttu-id="bfad4-171">따라서 이 샘플에서는 이러한 행을 사용하여 새 행을 데이터베이스에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-171">So, the sample uses these rows to insert the new rows into the database.</span></span>

- <span data-ttu-id="bfad4-172">이 샘플에서는 DataAdapter.TableMappings를 사용하여 소스 테이블과 DataTable 간의 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-172">The samples uses DataAdapter.TableMappings to define the mapping between the source table and DataTable.</span></span>

- <span data-ttu-id="bfad4-173">이 샘플에서는 DataAdapter.FillLoadOption을 사용하여 어댑터가 DbDataReader에서 DataTable을 채우는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-173">The sample uses DataAdapter.FillLoadOption to determine how the adapter fills the DataTable from the DbDataReader.</span></span> <span data-ttu-id="bfad4-174">DataTable을 만드는 경우 이 속성을 LoadOption.Upsert 또는 LoadOption.PreserveChanges로 설정하여 현재 버전이나 원래 버전에 데이터베이스의 데이터를 쓸 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-174">When you create a DataTable, you can only write the data from database to the current version or the original version by setting the property as the LoadOption.Upsert or the LoadOption.PreserveChanges.</span></span>

- <span data-ttu-id="bfad4-175">또한 이 샘플에서는 DbDataAdapter.UpdateBatchSize를 사용하여 배치 작업을 수행하는 방법으로 테이블을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-175">The sample will also update the table by using DbDataAdapter.UpdateBatchSize to perform batch operations.</span></span>

<span data-ttu-id="bfad4-176">샘플을 컴파일 및 실행하기 전에 다음과 같이 샘플 데이터베이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-176">Before you compile and run the sample, you need to create the sample database:</span></span>

```sql
USE [master]
GO

CREATE DATABASE [MySchool]

GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)

SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF

ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
```

<span data-ttu-id="bfad4-177">이 코드 샘플을 사용 하는 c # 및 Visual Basic 프로젝트는 [개발자 코드 샘플](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfad4-177">C# and Visual Basic projects with this code sample can be found on [Developer Code Samples](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.SqlClient;
using System.Linq;
using CSDataAdapterOperations.Properties;

namespace CSDataAdapterOperations.Properties {
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {

      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));

      public static Settings Default {
         get {
            return defaultInstance;
         }
      }

      [global::System.Configuration.ApplicationScopedSettingAttribute()]
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]
      public string MySchoolConnectionString {
         get {
            return ((string)(this["MySchoolConnectionString"]));
         }
      }
   }
}

class Program {
   static void Main(string[] args) {
      Settings settings = new Settings();

      // Copy the data from the database.  Get the table Department and Course from the database.
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]
                                     FROM [MySchool].[dbo].[Department];

                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]
                                   FROM [MySchool].[dbo].[Course]
                                   Group by [CourseID]";

      DataSet mySchool = new DataSet();

      SqlCommand selectCommand = new SqlCommand(selectString);
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);

      // Use DataTableMapping to map the source tables and the destination tables.
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);

      Console.WriteLine("The following tables are from the database.");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      // Roll back the changes
      DataTable department = mySchool.Tables["Department"];
      DataTable course = mySchool.Tables["Course"];

      department.Rows[0]["Name"] = "New" + department.Rows[0][1];
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];
      course.Rows[0]["Credits"] = 10;

      Console.WriteLine("After we changed the tables:");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      department.RejectChanges();
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");
      ShowDataTable(department);

      DataColumn[] primaryColumns = { course.Columns["CourseID"] };
      DataColumn[] resetColumns = { course.Columns["Title"] };
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");
      ShowDataTable(course);

      // Batch update the table.
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],
                                   [Credits],[DepartmentID])
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";
      SqlCommand insertCommand = new SqlCommand(insertString);
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");

      const Int32 batchSize = 10;
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);
   }

   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a
            // DataRow after it is added to the DataTable during any of the Fill operations.
            adapter.AcceptChangesDuringFill = false;

            adapter.Fill(dataSet);
         }
      }
   }

   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.
   private static void ResetCourse(DataTable table, String connectionString,
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {
      table.PrimaryKey = primaryColumns;

      // Build the query string
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));

      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");

      SqlCommand selectCommand = new SqlCommand(selectString);

      ResetDataTable(table, connectionString, selectCommand);
   }

   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges
   // The ResetDataTable method rolls back one or more columns of data.
   private static void ResetDataTable(DataTable table, String connectionString,
       SqlCommand selectCommand) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {
            // The incoming values for this row will be written to the current version of each
            // column. The original version of each column's data will not be changed.
            adapter.FillLoadOption = LoadOption.Upsert;

            adapter.Fill(table);
         }
      }
   }

   private static void BatchInsertUpdate(DataTable table, String connectionString,
       SqlCommand insertCommand, Int32 batchSize) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         insertCommand.Connection = connection;
         // When setting UpdateBatchSize to a value other than 1, all the commands
         // associated with the SqlDataAdapter have to have their UpdatedRowSource
         // property set to None or OutputParameters. An exception is thrown otherwise.
         insertCommand.UpdatedRowSource = UpdateRowSource.None;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter()) {
            adapter.InsertCommand = insertCommand;
            // Gets or sets the number of rows that are processed in each round-trip to the server.
            // Setting it to 1 disables batch updates, as rows are sent one at a time.
            adapter.UpdateBatchSize = batchSize;

            adapter.Update(table);

            Console.WriteLine("Successfully to update the table.");
         }
      }
   }

   private static void ShowDataTable(DataTable table) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-14}", col.ColumnName);
      }
      Console.WriteLine("{0,-14}", "RowState");

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-14:d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-14:C}", row[col]);
            else
               Console.Write("{0,-14}", row[col]);
         }
         Console.WriteLine("{0,-14}", row.RowState);
      }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="bfad4-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfad4-178">See also</span></span>

- [<span data-ttu-id="bfad4-179">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="bfad4-179">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="bfad4-180">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="bfad4-180">Row States and Row Versions</span></span>](./dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="bfad4-181">AcceptChanges 및 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="bfad4-181">AcceptChanges and RejectChanges</span></span>](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [<span data-ttu-id="bfad4-182">DataSet 콘텐츠 병합</span><span class="sxs-lookup"><span data-stu-id="bfad4-182">Merging DataSet Contents</span></span>](./dataset-datatable-dataview/merging-dataset-contents.md)
- [<span data-ttu-id="bfad4-183">ID 또는 일련 번호 값 검색</span><span class="sxs-lookup"><span data-stu-id="bfad4-183">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)
- [<span data-ttu-id="bfad4-184">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="bfad4-184">ADO.NET Overview</span></span>](ado-net-overview.md)
