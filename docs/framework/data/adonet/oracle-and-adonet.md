---
title: Oracle 및 ADO.NET
description: Oracle 호출 인터페이스를 사용 하 여 Oracle 데이터베이스에 대 한 액세스를 제공 하는 Oracle 용 .NET Framework Data Provider의 기능 및 동작에 대해 알아봅니다.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 736b8dc5179a15ec219c1dae06b9ee6b5d6c3ef3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166627"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="dc40d-103">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dc40d-103">Oracle and ADO.NET</span></span>

> [!NOTE]
> <span data-ttu-id="dc40d-104"><xref:System.Data.OracleClient>의 형식은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-104">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="dc40d-105">이 형식은 현재 버전의 .NET Framework에서 계속 지원되지만 향후 릴리스에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-105">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="dc40d-106">타사 Oracle 공급자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-106">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="dc40d-107">이 섹션에서는 Oracle의 .NET Framework Data Provider와 관련 된 기능 및 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-107">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="dc40d-108">Oracle의 .NET Framework Data Provider는 oracle 클라이언트 소프트웨어에서 제공 하는 OCI (Oracle Call Interface)를 사용 하 여 Oracle 데이터베이스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-108">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="dc40d-109">데이터 공급자의 기능은 SQL Server, OLE DB 및 ODBC에 대 한 .NET Framework 데이터 공급자와 유사 하 게 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-109">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="dc40d-110">Oracle에 대 한 .NET Framework Data Provider을 사용 하려면 응용 프로그램에서 다음과 <xref:System.Data.OracleClient> 같이 네임 스페이스를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-110">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="dc40d-111">또한 코드를 컴파일할 때 DLL에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-111">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="dc40d-112">예를 들어, C# 프로그램을 컴파일하는 경우 명령줄에 다음을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-112">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="dc40d-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="dc40d-113">In This Section</span></span>  

 [<span data-ttu-id="dc40d-114">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc40d-114">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="dc40d-115">Oracle의 .NET Framework Data Provider을 사용 하기 위한 요구 사항에 대해 설명 하 고이를 사용 하는 경우 알아야 할 몇 가지 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-115">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="dc40d-116">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="dc40d-116">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="dc40d-117">Oracle BFILE 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleBFile> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-117">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="dc40d-118">Oracle LOB</span><span class="sxs-lookup"><span data-stu-id="dc40d-118">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="dc40d-119">Oracle LOB 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleLob> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-119">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="dc40d-120">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="dc40d-120">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="dc40d-121">Oracle REF CURSOR 데이터 형식 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-121">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="dc40d-122">OracleType</span><span class="sxs-lookup"><span data-stu-id="dc40d-122">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="dc40d-123"><xref:System.Data.OracleClient.OracleNumber> 및 <xref:System.Data.OracleClient.OracleString>을 비롯하여 Oracle 데이터 형식 작업에 사용할 수 있는 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-123">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="dc40d-124">Oracle 시퀀스</span><span class="sxs-lookup"><span data-stu-id="dc40d-124">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="dc40d-125">서버에서 생성한 Oracle 시퀀스 키 값을 검색하는 지원 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-125">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="dc40d-126">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="dc40d-126">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="dc40d-127">Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-127">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="dc40d-128">Oracle 분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="dc40d-128">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="dc40d-129"><xref:System.Data.OracleClient.OracleConnection> 개체에서 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-129">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dc40d-130">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="dc40d-130">Related Sections</span></span>  

 [<span data-ttu-id="dc40d-131">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="dc40d-131">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="dc40d-132">ADO.NET을 사용할 때 보안 코드를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-132">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="dc40d-133">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="dc40d-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="dc40d-134">`DataSets`, 형식화된 `DataSets`, `DataTables` 및 `DataViews`를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-134">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="dc40d-135">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="dc40d-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="dc40d-136">ADO.NET에서 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-136">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="dc40d-137">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dc40d-137">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="dc40d-138">SQL Server 관련 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-138">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="dc40d-139">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="dc40d-139">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="dc40d-140">ADO.NET에서 공급자 독립적인 코드를 쓸 수 있게 하는 일반 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc40d-140">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc40d-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc40d-141">See also</span></span>

- [<span data-ttu-id="dc40d-142">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dc40d-142">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="dc40d-143">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="dc40d-143">ADO.NET Overview</span></span>](ado-net-overview.md)
