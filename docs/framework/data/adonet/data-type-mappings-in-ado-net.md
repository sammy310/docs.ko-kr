---
description: '자세한 정보: ADO.NET의 데이터 형식 매핑'
title: 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: c1829fdc2ebc053d1fd3a76e827a81e582572233
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786448"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="cac92-103">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cac92-103">Data Type Mappings in ADO.NET</span></span>

<span data-ttu-id="cac92-104">.NET Framework는 런타임에 형식이 선언, 사용 및 관리되는 방법을 정의하는 공용 형식 시스템을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-104">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="cac92-105">.NET Framework는 값 형식과 참조 형식으로 구성되며, 두 형식 모두 <xref:System.Object> 기본 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-105">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="cac92-106">데이터 소스로 작업할 경우 데이터 형식을 명시적으로 지정하지 않으면 데이터 공급자에서 데이터 형식이 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-106">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="cac92-107">예를 들어 <xref:System.Data.DataSet> 개체는 모든 데이터 소스에 대해 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-107">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="cac92-108">`DataSet`의 데이터는 데이터 소스에서 검색되며 변경 내용은 `DataAdapter`를 사용하여 데이터 소스에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-108">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="cac92-109">즉,가의을 `DataAdapter` <xref:System.Data.DataTable> `DataSet` 데이터 소스의 값으로 채울 때에 있는 열의 결과 데이터 형식은 `DataTable` 데이터 원본에 연결 하는 데 사용 되는 .NET Framework 데이터 공급자와 관련 된 형식이 아닌 .NET Framework 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-109">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="cac92-110">마찬가지로 `DataReader`가 데이터 원본에서 값을 반환하면 결과 값은 .NET Framework 유형을 가진 로컬 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-110">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="cac92-111">의 작업과의 `Fill` `DataAdapter` `Get` 메서드 모두 `DataReader` .NET Framework 형식은 .NET Framework 데이터 공급자에서 반환 된 값에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-111">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="cac92-112">반환되는 값의 형식을 알고 있는 경우에는 유추되는 데이터 형식을 사용하는 대신 `DataReader`의 형식화된 접근자 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-112">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="cac92-113">형식화된 접근자 메서드는 특정 .NET Framework 형식으로 값을 반환하여 더 나은 성능을 제공하므로 추가 형식 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-113">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cac92-114">.NET Framework 데이터 공급자 데이터 형식의 Null 값은로 표시 됩니다 `DBNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="cac92-114">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cac92-115">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cac92-115">In This Section</span></span>  

 [<span data-ttu-id="cac92-116">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cac92-116">SQL Server Data Type Mappings</span></span>](sql-server-data-type-mappings.md)  
 <span data-ttu-id="cac92-117"><xref:System.Data.SqlClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-117">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="cac92-118">OLE DB 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cac92-118">OLE DB Data Type Mappings</span></span>](ole-db-data-type-mappings.md)  
 <span data-ttu-id="cac92-119"><xref:System.Data.OleDb>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-119">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="cac92-120">ODBC 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cac92-120">ODBC Data Type Mappings</span></span>](odbc-data-type-mappings.md)  
 <span data-ttu-id="cac92-121"><xref:System.Data.Odbc>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-121">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="cac92-122">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="cac92-122">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="cac92-123"><xref:System.Data.OracleClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-123">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="cac92-124">부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="cac92-124">Floating-Point Numbers</span></span>](floating-point-numbers.md)  
 <span data-ttu-id="cac92-125">개발자가 부동 소수점 숫자를 사용할 때 자주 발생하는 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cac92-125">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac92-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cac92-126">See also</span></span>

- [<span data-ttu-id="cac92-127">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cac92-127">SQL Server Data Types and ADO.NET</span></span>](./sql/sql-server-data-types.md)
- [<span data-ttu-id="cac92-128">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="cac92-128">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="cac92-129">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="cac92-129">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="cac92-130">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="cac92-130">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="cac92-131">[형식 변환](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cac92-131">[Converting Types](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="cac92-132">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="cac92-132">ADO.NET Overview</span></span>](ado-net-overview.md)
