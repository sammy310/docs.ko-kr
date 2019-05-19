---
title: Oracle 및 ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 012a5b55d052f5f06da5c152da79f4676b2bff4e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877955"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="aeb1c-102">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aeb1c-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="aeb1c-103"><xref:System.Data.OracleClient>의 형식은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="aeb1c-104">이 형식은 현재 버전의 .NET Framework에서 계속 지원되지만 향후 릴리스에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="aeb1c-105">타사 Oracle 공급자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="aeb1c-106">이 섹션에서는 기능 및.NET Framework Data Provider for Oracle에 관련 된 동작에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="aeb1c-107">.NET Framework Data Provider for Oracle 호출 인터페이스 OCI (Oracle)를 사용 하 여 Oracle 클라이언트 소프트웨어에서 제공 하는 Oracle 데이터베이스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="aeb1c-108">데이터 공급자의 기능은 SQL Server, OLE DB 및 ODBC 용.NET Framework 데이터 공급자와 비슷한 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="aeb1c-109">.NET Framework Data Provider for Oracle를 사용 하려면 응용 프로그램 참조 해야 합니다는 <xref:System.Data.OracleClient> 같이 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="aeb1c-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="aeb1c-110">또한 코드를 컴파일할 때 DLL에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="aeb1c-111">예를 들어, C# 프로그램을 컴파일하는 경우 명령줄에 다음을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="aeb1c-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="aeb1c-112">In This Section</span></span>  
 [<span data-ttu-id="aeb1c-113">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="aeb1c-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="aeb1c-114">.NET Framework Data Provider for Oracle을 사용 하 여 요구 사항을 설명 하 고 다양 한 사용 하는 경우 주의 해야 할 문제를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="aeb1c-115">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="aeb1c-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="aeb1c-116">Oracle BFILE 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleBFile> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="aeb1c-117">Oracle LOB</span><span class="sxs-lookup"><span data-stu-id="aeb1c-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="aeb1c-118">Oracle LOB 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleLob> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="aeb1c-119">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="aeb1c-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="aeb1c-120">Oracle REF CURSOR 데이터 형식 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="aeb1c-121">OracleType</span><span class="sxs-lookup"><span data-stu-id="aeb1c-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="aeb1c-122"><xref:System.Data.OracleClient.OracleNumber> 및 <xref:System.Data.OracleClient.OracleString>을 비롯하여 Oracle 데이터 형식 작업에 사용할 수 있는 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="aeb1c-123">Oracle 시퀀스</span><span class="sxs-lookup"><span data-stu-id="aeb1c-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="aeb1c-124">서버에서 생성한 Oracle 시퀀스 키 값을 검색하는 지원 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="aeb1c-125">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="aeb1c-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="aeb1c-126">Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="aeb1c-127">Oracle 분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="aeb1c-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="aeb1c-128"><xref:System.Data.OracleClient.OracleConnection> 개체에서 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aeb1c-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="aeb1c-129">Related Sections</span></span>  
 [<span data-ttu-id="aeb1c-130">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="aeb1c-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="aeb1c-131">ADO.NET을 사용할 때 보안 코드를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="aeb1c-132">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="aeb1c-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="aeb1c-133">`DataSets`, 형식화된 `DataSets`, `DataTables` 및 `DataViews`를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="aeb1c-134">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="aeb1c-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="aeb1c-135">ADO.NET에서 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="aeb1c-136">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aeb1c-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="aeb1c-137">SQL Server 관련 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="aeb1c-138">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="aeb1c-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="aeb1c-139">ADO.NET에서 공급자 독립적인 코드를 쓸 수 있게 하는 일반 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb1c-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb1c-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="aeb1c-140">See also</span></span>

- [<span data-ttu-id="aeb1c-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aeb1c-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="aeb1c-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="aeb1c-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
