---
description: '자세한 정보: 데이터베이스 액세스 작업'
title: Database Access Activities
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 421da4a55997dac62ccc5c598bc401a20711ec61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792546"
---
# <a name="database-access-activities"></a><span data-ttu-id="3bb86-103">Database Access Activities</span><span class="sxs-lookup"><span data-stu-id="3bb86-103">Database Access Activities</span></span>

<span data-ttu-id="3bb86-104">데이터베이스 액세스 활동을 사용하여 워크플로 내에서 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-104">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="3bb86-105">이러한 작업을 통해 데이터베이스에 액세스 하 여 정보를 검색 하거나 수정 하 고 [ADO.NET](../../data/adonet/index.md) 을 사용 하 여 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-105">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bb86-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3bb86-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3bb86-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3bb86-108">이 디렉터리가 없으면 (다운로드 페이지)로 이동 하 여 모든 Windows Communication Foundation (WCF) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-108">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3bb86-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="3bb86-110">데이터베이스 활동</span><span class="sxs-lookup"><span data-stu-id="3bb86-110">Database Activities</span></span>

<span data-ttu-id="3bb86-111">다음 단원에서는 이 샘플에 포함된 활동 목록에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-111">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="3bb86-112">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="3bb86-112">DbUpdate</span></span>

<span data-ttu-id="3bb86-113">데이터베이스의 내용을 수정(삽입, 업데이트, 삭제 등)하는 SQL 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-113">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

<span data-ttu-id="3bb86-114">이 클래스는 <xref:System.Activities.AsyncCodeActivity>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-114">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="3bb86-115">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 애플리케이션 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-115">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="3bb86-116">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-116">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="3bb86-117">`DbUpdate`가 실행된 후에는 영향을 받은 레코드의 수가 `AffectedRecords` 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-117">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|<span data-ttu-id="3bb86-118">인수</span><span class="sxs-lookup"><span data-stu-id="3bb86-118">Argument</span></span>|<span data-ttu-id="3bb86-119">설명</span><span class="sxs-lookup"><span data-stu-id="3bb86-119">Description</span></span>|
|-|-|
|<span data-ttu-id="3bb86-120">ProviderName</span><span class="sxs-lookup"><span data-stu-id="3bb86-120">ProviderName</span></span>|<span data-ttu-id="3bb86-121">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-121">ADO.NET provider invariant name.</span></span> <span data-ttu-id="3bb86-122">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-122">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="3bb86-123">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="3bb86-123">ConnectionString</span></span>|<span data-ttu-id="3bb86-124">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-124">Connection string to connect to the database.</span></span> <span data-ttu-id="3bb86-125">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-125">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="3bb86-126">ConfigName</span><span class="sxs-lookup"><span data-stu-id="3bb86-126">ConfigName</span></span>|<span data-ttu-id="3bb86-127">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-127">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="3bb86-128">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-128">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="3bb86-129">CommandType</span><span class="sxs-lookup"><span data-stu-id="3bb86-129">CommandType</span></span>|<span data-ttu-id="3bb86-130">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-130">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="3bb86-131">Sql</span><span class="sxs-lookup"><span data-stu-id="3bb86-131">Sql</span></span>|<span data-ttu-id="3bb86-132">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-132">The SQL command to be executed.</span></span>|
|<span data-ttu-id="3bb86-133">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb86-133">Parameters</span></span>|<span data-ttu-id="3bb86-134">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-134">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="3bb86-135">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="3bb86-135">AffectedRecords</span></span>|<span data-ttu-id="3bb86-136">마지막 작업의 영향을 받은 레코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-136">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="3bb86-137">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="3bb86-137">DbQueryScalar</span></span>

<span data-ttu-id="3bb86-138">데이터베이스에서 단일 값을 검색하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-138">Executes a query that retrieves a single value from the database.</span></span>

<span data-ttu-id="3bb86-139">이 클래스는 <xref:System.Activities.AsyncCodeActivity%601>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-139">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="3bb86-140">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 애플리케이션 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-140">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="3bb86-141">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-141">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="3bb86-142">가 실행 된 후에는 `DbQueryScalar` `Result out` `TResult` 기본 클래스에 정의 된 형식의 인수에서 스칼라가 반환 됩니다 <xref:System.Activities.AsyncCodeActivity%601> .</span><span class="sxs-lookup"><span data-stu-id="3bb86-142">After `DbQueryScalar` is executed, the scalar is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="3bb86-143">인수</span><span class="sxs-lookup"><span data-stu-id="3bb86-143">Argument</span></span>|<span data-ttu-id="3bb86-144">설명</span><span class="sxs-lookup"><span data-stu-id="3bb86-144">Description</span></span>|
|-|-|
|<span data-ttu-id="3bb86-145">ProviderName</span><span class="sxs-lookup"><span data-stu-id="3bb86-145">ProviderName</span></span>|<span data-ttu-id="3bb86-146">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-146">ADO.NET provider invariant name.</span></span> <span data-ttu-id="3bb86-147">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-147">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="3bb86-148">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="3bb86-148">ConnectionString</span></span>|<span data-ttu-id="3bb86-149">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-149">Connection string to connect to the database.</span></span> <span data-ttu-id="3bb86-150">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-150">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="3bb86-151">ConfigName</span><span class="sxs-lookup"><span data-stu-id="3bb86-151">ConfigName</span></span>|<span data-ttu-id="3bb86-152">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-152">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="3bb86-153">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-153">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="3bb86-154">CommandType</span><span class="sxs-lookup"><span data-stu-id="3bb86-154">CommandType</span></span>|<span data-ttu-id="3bb86-155">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-155">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="3bb86-156">Sql</span><span class="sxs-lookup"><span data-stu-id="3bb86-156">Sql</span></span>|<span data-ttu-id="3bb86-157">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-157">The SQL command to be executed.</span></span>|
|<span data-ttu-id="3bb86-158">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb86-158">Parameters</span></span>|<span data-ttu-id="3bb86-159">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-159">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="3bb86-160">결과</span><span class="sxs-lookup"><span data-stu-id="3bb86-160">Result</span></span>|<span data-ttu-id="3bb86-161">쿼리가 실행된 후에 얻은 스칼라입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-161">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="3bb86-162">이 인수는 `TResult` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-162">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="3bb86-163">DbQuery</span><span class="sxs-lookup"><span data-stu-id="3bb86-163">DbQuery</span></span>

<span data-ttu-id="3bb86-164">개체 목록을 검색하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-164">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="3bb86-165">쿼리가 실행 된 후 매핑 함수가 실행 됩니다 ( <xref:System.Func%601> < `DbDataReader` , `TResult`> 또는 <xref:System.Activities.ActivityFunc%601> < `DbDataReader` `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="3bb86-165">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="3bb86-166">이 매핑 함수는 `DbDataReader`에서 레코드를 가져오고 이를 반환할 개체에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-166">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

<span data-ttu-id="3bb86-167">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 애플리케이션 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-167">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="3bb86-168">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-168">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="3bb86-169">SQL 쿼리의 결과는 `DbDataReader`를 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-169">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="3bb86-170">활동에서는 `DbDataReader`를 반복하고 `DbDataReader`의 행을 `TResult`의 인스턴스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-170">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="3bb86-171">의 사용자는 `DbQuery` 매핑 코드를 제공 해야 하며이 작업은 <xref:System.Func%601> < `DbDataReader` , `TResult`> 또는 <xref:System.Activities.ActivityFunc%601> < `DbDataReader` `TResult`>를 사용 하는 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-171">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="3bb86-172">첫 번째의 경우에는 단일 실행 펄스에서 매핑이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-172">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="3bb86-173">따라서 속도가 더 빠르지만 매핑이 XAML로 serialize될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-173">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="3bb86-174">두 번째의 경우에는 매핑이 여러 펄스에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-174">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="3bb86-175">따라서 속도가 더 느릴 수 있지만, 매핑이 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-175">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|<span data-ttu-id="3bb86-176">인수</span><span class="sxs-lookup"><span data-stu-id="3bb86-176">Argument</span></span>|<span data-ttu-id="3bb86-177">설명</span><span class="sxs-lookup"><span data-stu-id="3bb86-177">Description</span></span>|
|-|-|
|<span data-ttu-id="3bb86-178">ProviderName</span><span class="sxs-lookup"><span data-stu-id="3bb86-178">ProviderName</span></span>|<span data-ttu-id="3bb86-179">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-179">ADO.NET provider invariant name.</span></span> <span data-ttu-id="3bb86-180">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-180">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="3bb86-181">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="3bb86-181">ConnectionString</span></span>|<span data-ttu-id="3bb86-182">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-182">Connection string to connect to the database.</span></span> <span data-ttu-id="3bb86-183">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-183">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="3bb86-184">ConfigName</span><span class="sxs-lookup"><span data-stu-id="3bb86-184">ConfigName</span></span>|<span data-ttu-id="3bb86-185">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-185">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="3bb86-186">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-186">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="3bb86-187">CommandType</span><span class="sxs-lookup"><span data-stu-id="3bb86-187">CommandType</span></span>|<span data-ttu-id="3bb86-188">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-188">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="3bb86-189">Sql</span><span class="sxs-lookup"><span data-stu-id="3bb86-189">Sql</span></span>|<span data-ttu-id="3bb86-190">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-190">The SQL command to be executed.</span></span>|
|<span data-ttu-id="3bb86-191">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb86-191">Parameters</span></span>|<span data-ttu-id="3bb86-192">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-192">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="3bb86-193">Mapper</span><span class="sxs-lookup"><span data-stu-id="3bb86-193">Mapper</span></span>|<span data-ttu-id="3bb86-194"><xref:System.Func%601> < `DbDataReader` `TResult` 쿼리 실행 결과로 얻은의 레코드를 사용 하 `DataReader` 고 `TResult` 컬렉션에 추가할 형식의 개체 인스턴스를 반환 하는 매핑 함수 (,>)입니다 `Result` .</span><span class="sxs-lookup"><span data-stu-id="3bb86-194">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="3bb86-195">이 경우 매핑은 단일 실행 펄스에서 수행되지만 디자이너를 사용하여 선언적으로 작성될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-195">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="3bb86-196">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="3bb86-196">MapperFunc</span></span>|<span data-ttu-id="3bb86-197"><xref:System.Activities.ActivityFunc%601> < `DbDataReader` `TResult` 쿼리 실행 결과로 얻은의 레코드를 사용 하 `DataReader` 고 `TResult` 컬렉션에 추가할 형식의 개체 인스턴스를 반환 하는 매핑 함수 (,>)입니다 `Result` .</span><span class="sxs-lookup"><span data-stu-id="3bb86-197">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="3bb86-198">이 경우에는 여러 실행 펄스에서 매핑이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-198">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="3bb86-199">이 함수는 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-199">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="3bb86-200">결과</span><span class="sxs-lookup"><span data-stu-id="3bb86-200">Result</span></span>|<span data-ttu-id="3bb86-201">쿼리를 실행하고 `DataReader`의 각 레코드에 대해 매핑 함수를 실행한 결과로 얻은 개체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-201">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="3bb86-202">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="3bb86-202">DbQueryDataSet</span></span>

<span data-ttu-id="3bb86-203"><xref:System.Data.DataSet>을 반환하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-203">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="3bb86-204">이 클래스는 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-204">This class performs its work asynchronously.</span></span> <span data-ttu-id="3bb86-205">>에서 파생 되 <xref:System.Activities.AsyncCodeActivity> < `TResult` 고 비동기 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-205">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

<span data-ttu-id="3bb86-206">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 애플리케이션 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-206">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="3bb86-207">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-207">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="3bb86-208">가 실행 된 후는 `DbQueryDataSet` `DataSet` `Result out` `TResult` 기본 클래스에 정의 된 형식의 인수에서 반환 됩니다 <xref:System.Activities.AsyncCodeActivity%601> .</span><span class="sxs-lookup"><span data-stu-id="3bb86-208">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="3bb86-209">인수</span><span class="sxs-lookup"><span data-stu-id="3bb86-209">Argument</span></span>|<span data-ttu-id="3bb86-210">설명</span><span class="sxs-lookup"><span data-stu-id="3bb86-210">Description</span></span>|
|-|-|
|<span data-ttu-id="3bb86-211">ProviderName</span><span class="sxs-lookup"><span data-stu-id="3bb86-211">ProviderName</span></span>|<span data-ttu-id="3bb86-212">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-212">ADO.NET provider invariant name.</span></span> <span data-ttu-id="3bb86-213">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-213">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="3bb86-214">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="3bb86-214">ConnectionString</span></span>|<span data-ttu-id="3bb86-215">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-215">Connection string to connect to the database.</span></span> <span data-ttu-id="3bb86-216">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-216">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="3bb86-217">ConfigName</span><span class="sxs-lookup"><span data-stu-id="3bb86-217">ConfigName</span></span>|<span data-ttu-id="3bb86-218">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-218">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="3bb86-219">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-219">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="3bb86-220">CommandType</span><span class="sxs-lookup"><span data-stu-id="3bb86-220">CommandType</span></span>|<span data-ttu-id="3bb86-221">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-221">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="3bb86-222">Sql</span><span class="sxs-lookup"><span data-stu-id="3bb86-222">Sql</span></span>|<span data-ttu-id="3bb86-223">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-223">The SQL command to be executed.</span></span>|
|<span data-ttu-id="3bb86-224">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb86-224">Parameters</span></span>|<span data-ttu-id="3bb86-225">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-225">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="3bb86-226">결과</span><span class="sxs-lookup"><span data-stu-id="3bb86-226">Result</span></span>|<span data-ttu-id="3bb86-227">쿼리가 실행된 후에 얻은 <xref:System.Data.DataSet>입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-227"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="3bb86-228">연결 정보 구성</span><span class="sxs-lookup"><span data-stu-id="3bb86-228">Configuring Connection Information</span></span>

<span data-ttu-id="3bb86-229">모든 DbActivity는 동일한 구성 매개 변수를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-229">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="3bb86-230">다음과 같은 두 가지 방법으로 DbActivity를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-230">They can be configured in two ways:</span></span>

- <span data-ttu-id="3bb86-231">`ConnectionString + InvariantName`: ADO.NET 공급자 고정 이름과 연결 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-231">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- <span data-ttu-id="3bb86-232">`ConfigName`: 연결 정보를 포함하는 구성 파일 섹션의 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-232">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- <span data-ttu-id="3bb86-233">활동에서는 다음과 같이 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-233">In the activity:</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a><span data-ttu-id="3bb86-234">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="3bb86-234">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="3bb86-235">설치 지침</span><span class="sxs-lookup"><span data-stu-id="3bb86-235">Setup instructions</span></span>

<span data-ttu-id="3bb86-236">이 샘플에서는 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-236">This sample uses a database.</span></span> <span data-ttu-id="3bb86-237">샘플과 함께 설치 및 로드 스크립트(Setup.cmd)가 제공되며,</span><span class="sxs-lookup"><span data-stu-id="3bb86-237">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="3bb86-238">이 파일은 명령 프롬프트를 사용하여 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-238">You must execute that file using the command prompt.</span></span>

<span data-ttu-id="3bb86-239">Setup.cmd 스크립트는 다음을 수행하는 SQL 명령이 포함된 CreateDb.sql 스크립트 파일을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-239">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

- <span data-ttu-id="3bb86-240">DbActivitiesSample이라는 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-240">Creates a database called DbActivitiesSample.</span></span>

- <span data-ttu-id="3bb86-241">Roles 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-241">Creates the Roles table.</span></span>

- <span data-ttu-id="3bb86-242">Employees 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-242">Creates Employees table.</span></span>

- <span data-ttu-id="3bb86-243">Roles 테이블에 3개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-243">Inserts three records into the Roles table.</span></span>

- <span data-ttu-id="3bb86-244">Employees 테이블에 12개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-244">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="3bb86-245">Setup.cmd를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3bb86-245">To run Setup.cmd</span></span>

1. <span data-ttu-id="3bb86-246">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-246">Open a command prompt.</span></span>

2. <span data-ttu-id="3bb86-247">DbActivities 샘플 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-247">Go to the DbActivities sample folder.</span></span>

3. <span data-ttu-id="3bb86-248">"Setup.exe"를 입력 하 고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-248">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3bb86-249">Setup.cmd에서는 로컬 컴퓨터의 SqlExpress 인스턴스에 샘플을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-249">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="3bb86-250">다른 SQL 서버 인스턴스에 샘플을 설치하려면 Setup.cmd를 새 인스턴스 이름으로 편집하세요.</span><span class="sxs-lookup"><span data-stu-id="3bb86-250">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="3bb86-251">샘플 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="3bb86-251">To uninstall the sample database</span></span>

1. <span data-ttu-id="3bb86-252">명령 프롬프트에서 샘플 폴더로 이동하여 Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-252">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="3bb86-253">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3bb86-253">To run the sample</span></span>

1. <span data-ttu-id="3bb86-254">Visual Studio 2010에서 솔루션 열기</span><span class="sxs-lookup"><span data-stu-id="3bb86-254">Open the solution in Visual Studio 2010</span></span>

2. <span data-ttu-id="3bb86-255">Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-255">To compile the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="3bb86-256">Ctrl+F5를 눌러 샘플을 디버깅하지 않고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-256">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bb86-257">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-257">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3bb86-258">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3bb86-258">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3bb86-259">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-259">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3bb86-260">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb86-260">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
