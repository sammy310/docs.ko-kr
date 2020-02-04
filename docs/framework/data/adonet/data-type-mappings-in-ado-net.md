---
title: 데이터 형식 매핑
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 610cdc1a679b0c51125075076120e12db97da421
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980199"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="290b8-102">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="290b8-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="290b8-103">.NET Framework는 런타임에 형식이 선언, 사용 및 관리되는 방법을 정의하는 공용 형식 시스템을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="290b8-104">.NET Framework는 값 형식과 참조 형식으로 구성되며, 두 형식 모두 <xref:System.Object> 기본 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="290b8-105">데이터 소스로 작업할 경우 데이터 형식을 명시적으로 지정하지 않으면 데이터 공급자에서 데이터 형식이 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="290b8-106">예를 들어 <xref:System.Data.DataSet> 개체는 모든 데이터 소스에 대해 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="290b8-107">`DataSet`의 데이터는 데이터 소스에서 검색되며 변경 내용은 `DataAdapter`를 사용하여 데이터 소스에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="290b8-108">즉, `DataAdapter`에서 `DataSet`의 <xref:System.Data.DataTable>를 데이터 원본의 값으로 채울 때 `DataTable`에 있는 열의 결과 데이터 형식은 데이터 원본에 연결 하는 데 사용 되는 .NET Framework 데이터 공급자와 관련 된 형식이 아닌 .NET Framework 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="290b8-109">마찬가지로 `DataReader`이 데이터 원본에서 값을 반환 하는 경우 결과 값은 .NET Framework 형식의 지역 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="290b8-110">`DataAdapter` `Fill` 작업과 `DataReader`의 `Get` 메서드 모두 .NET Framework 데이터 공급자에서 반환 된 값에서 .NET Framework 형식이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="290b8-111">반환되는 값의 형식을 알고 있는 경우에는 유추되는 데이터 형식을 사용하는 대신 `DataReader`의 형식화된 접근자 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="290b8-112">형식화 된 접근자 메서드는 값을 특정 .NET Framework 형식으로 반환 하 여 더 나은 성능을 제공 하므로 추가 형식 변환이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-112">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="290b8-113">.NET Framework 데이터 공급자 데이터 형식에 대 한 Null 값은 `DBNull.Value`으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-113">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="290b8-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="290b8-114">In This Section</span></span>  
 [<span data-ttu-id="290b8-115">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="290b8-115">SQL Server Data Type Mappings</span></span>](sql-server-data-type-mappings.md)  
 <span data-ttu-id="290b8-116"><xref:System.Data.SqlClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="290b8-117">OLE DB 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="290b8-117">OLE DB Data Type Mappings</span></span>](ole-db-data-type-mappings.md)  
 <span data-ttu-id="290b8-118"><xref:System.Data.OleDb>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="290b8-119">ODBC 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="290b8-119">ODBC Data Type Mappings</span></span>](odbc-data-type-mappings.md)  
 <span data-ttu-id="290b8-120"><xref:System.Data.Odbc>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="290b8-121">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="290b8-121">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="290b8-122"><xref:System.Data.OracleClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="290b8-123">부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="290b8-123">Floating-Point Numbers</span></span>](floating-point-numbers.md)  
 <span data-ttu-id="290b8-124">개발자가 부동 소수점 숫자를 사용할 때 자주 발생하는 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="290b8-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290b8-125">참조</span><span class="sxs-lookup"><span data-stu-id="290b8-125">See also</span></span>

- [<span data-ttu-id="290b8-126">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="290b8-126">SQL Server Data Types and ADO.NET</span></span>](./sql/sql-server-data-types.md)
- [<span data-ttu-id="290b8-127">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="290b8-127">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="290b8-128">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="290b8-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="290b8-129">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="290b8-129">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="290b8-130">[형식 변환](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="290b8-130">[Converting Types](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="290b8-131">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="290b8-131">ADO.NET Overview</span></span>](ado-net-overview.md)
