---
description: '자세한 정보: Entity Framework의 SqlClient에서 알려진 문제'
title: Entity Framework용 SqlClient에서 알려진 문제
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: c1a82657f1b43cddb858692d055df3bf2dca47ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697337"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a><span data-ttu-id="4368a-103">Entity Framework용 SqlClient에서 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4368a-103">Known Issues in SqlClient for Entity Framework</span></span>

<span data-ttu-id="4368a-104">이 단원에서는 .NET Framework Data Provider for SQL Server(SqlClient)와 관련된 알려진 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-104">This section describes known issues related to the .NET Framework Data Provider for SQL Server (SqlClient).</span></span>  
  
## <a name="trailing-spaces-in-string-functions"></a><span data-ttu-id="4368a-105">문자열 함수의 후행 공백</span><span class="sxs-lookup"><span data-stu-id="4368a-105">Trailing Spaces in String Functions</span></span>  

 <span data-ttu-id="4368a-106">SQL Server는 문자열 값에서 후행 공백을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-106">SQL Server ignores trailing spaces in string values.</span></span> <span data-ttu-id="4368a-107">따라서 문자열에 후행 공백을 전달하면 예기치 않은 결과가 발생하며 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-107">Therefore, passing trailing spaces in the string can lead to unpredictable results, even failures.</span></span>  
  
 <span data-ttu-id="4368a-108">문자열에 후행 공백이 있어야 하는 경우에는 SQL Server에서 문자열을 자르지 않도록 끝에 공백 문자를 추가 하는 것을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-108">If you have to have trailing spaces in your string, you should consider appending a white space character at the end, so that SQL Server does not trim the string.</span></span> <span data-ttu-id="4368a-109">후행 공백이 필요하지 않은 경우 쿼리 파이프라인을 통해 전달하기 전에 트리밍해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-109">If the trailing spaces are not required, they should be trimmed before they are passed down the query pipeline.</span></span>  
  
## <a name="right-function"></a><span data-ttu-id="4368a-110">RIGHT 함수</span><span class="sxs-lookup"><span data-stu-id="4368a-110">RIGHT Function</span></span>  

 <span data-ttu-id="4368a-111">`null`이 아닌 값을 첫 번째 인수, 0을 두 번째 인수로 `RIGHT(nvarchar(max)`, 0`)` 또는 `RIGHT(varchar(max)`, 0`)`에 전달하면 `NULL` 문자열 대신 `empty` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-111">If a non-`null` value is passed as a first argument and 0 is passed as a second argument to `RIGHT(nvarchar(max)`, 0`)` or `RIGHT(varchar(max)`, 0`)`, a `NULL` value will be returned instead of an `empty` string.</span></span>  
  
## <a name="cross-and-outer-apply-operators"></a><span data-ttu-id="4368a-112">CROSS 및 OUTER APPLY 연산자</span><span class="sxs-lookup"><span data-stu-id="4368a-112">CROSS and OUTER APPLY Operators</span></span>  

 <span data-ttu-id="4368a-113">CROSS 및 OUTER APPLY 연산자는 SQL Server 2005에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-113">CROSS and OUTER APPLY operators were introduced in SQL Server 2005.</span></span> <span data-ttu-id="4368a-114">경우에 따라 쿼리 파이프라인에서 CROSS APPLY 및/또는 OUTER APPLY 연산자가 포함된 Transact-SQL 문을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-114">In some cases the query pipeline might produce a Transact-SQL statement that contains CROSS APPLY and/or OUTER APPLY operators.</span></span> <span data-ttu-id="4368a-115">SQL Server 2005 이전 SQL Server 버전을 비롯 한 일부 백엔드 공급자는 이러한 연산자를 지원 하지 않으므로 이러한 백 엔드 공급자에서는 이러한 쿼리를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-115">Because some backend providers, including versions of SQL Server earlier than SQL Server 2005, do not support these operators, such queries cannot be executed on these backend providers.</span></span>  
  
 <span data-ttu-id="4368a-116">다음은 출력 쿼리에 CROSS APPLY 및/또는 OUTER APPLY 연산자가 포함될 수 있는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-116">The following are some typical scenarios that might lead to the presence of CROSS APPLY and/or OUTER APPLY operators in the output query:</span></span>  
  
- <span data-ttu-id="4368a-117">페이징이 있는 상호 관련된 하위 쿼리</span><span class="sxs-lookup"><span data-stu-id="4368a-117">A correlated subquery with paging.</span></span>  
  
- <span data-ttu-id="4368a-118">상호 관련된 하위 쿼리 또는 탐색으로 생성된 컬렉션에 대한 `AnyElement`</span><span class="sxs-lookup"><span data-stu-id="4368a-118">An `AnyElement` over a correlated sub-query, or over a collection produced by navigation.</span></span>  
  
- <span data-ttu-id="4368a-119">요소 선택기를 허용하는 그룹화 메서드를 사용하는 LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="4368a-119">LINQ queries that use grouping methods that accept an element selector.</span></span>  
  
- <span data-ttu-id="4368a-120">CROSS APPLY 또는 OUTER APPLY가 명시적으로 지정된 쿼리</span><span class="sxs-lookup"><span data-stu-id="4368a-120">A query in which a CROSS APPLY or an OUTER APPLY is explicitly specified</span></span>  
  
- <span data-ttu-id="4368a-121">REF 구문보다 DEREF 구문을 우선 적용하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="4368a-121">A query that has a DEREF construct over a REF construct.</span></span>  
  
## <a name="skip-operator"></a><span data-ttu-id="4368a-122">SKIP 연산자</span><span class="sxs-lookup"><span data-stu-id="4368a-122">SKIP Operator</span></span>  

 <span data-ttu-id="4368a-123">SQL Server 2000를 사용 하는 경우 키가 아닌 열에 ORDER BY와 함께 SKIP을 사용 하면 잘못 된 결과가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-123">If you are using SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="4368a-124">키가 아닌 열에 중복 데이터가 있는 경우, 지정된 개수 이상의 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-124">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="4368a-125">이는 SQL Server 2000에 대해 SKIP이 변환 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-125">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="4368a-126">예를 들어 다음 쿼리에서 `E.NonKeyColumn`에 중복 값이 있으면 5개가 넘는 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-126">For example, in the following query, more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
  
```sql  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a><span data-ttu-id="4368a-127">올바른 SQL Server 버전을 대상으로 지정</span><span class="sxs-lookup"><span data-stu-id="4368a-127">Targeting the Correct SQL Server Version</span></span>  

 <span data-ttu-id="4368a-128">Entity Framework는 `ProviderManifestToken` 저장소 모델 파일 (ssdl)에 있는 Schema 요소의 특성에 지정 된 SQL Server 버전에 따라 transact-sql 쿼리를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-128">The Entity Framework targets the Transact-SQL query based on the SQL Server version that is specified in the `ProviderManifestToken` attribute of the Schema element in the storage model (.ssdl) file.</span></span> <span data-ttu-id="4368a-129">이 버전은 연결된 실제 SQL Server의 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-129">This version might differ from the version of the actual SQL Server you are connected to.</span></span> <span data-ttu-id="4368a-130">예를 들어 SQL Server 2005를 사용 하지만 `ProviderManifestToken` 특성이 2008로 설정 된 경우 생성 된 transact-sql 쿼리가 서버에서 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-130">For example, if you are using SQL Server 2005, but your `ProviderManifestToken` attribute is set to 2008, the generated Transact-SQL query might not execute on the server.</span></span> <span data-ttu-id="4368a-131">예를 들어 SQL Server 2008에서 도입된 새 날짜 시간 형식을 사용하는 쿼리는 이전 버전의 SQL Server에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-131">For example, a query that uses the new date time types that were introduced in SQL Server 2008 will not execute on earlier versions of the SQL Server.</span></span> <span data-ttu-id="4368a-132">SQL Server 2005를 사용 하지만 `ProviderManifestToken` 특성이 2000로 설정 되어 있으면 생성 된 transact-sql 쿼리가 더 이상 최적화 되지 않을 수 있습니다. 그렇지 않으면 쿼리가 지원 되지 않는다는 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-132">If you are using SQL Server 2005, but your `ProviderManifestToken` attribute is set to 2000, the generated Transact-SQL query might be less optimized, or you might get an exception that says that the query is not supported.</span></span> <span data-ttu-id="4368a-133">자세한 내용은 이 항목의 앞부분에 있는 CROSS 및 OUTER APPLY 연산자 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4368a-133">For more information, see the CROSS and OUTER APPLY Operators section, earlier in this topic.</span></span>  
  
 <span data-ttu-id="4368a-134">특정 데이터베이스 동작은 데이터베이스로 설정된 호환성 수준에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-134">Certain database behaviors depend on the compatibility level set to the database.</span></span> <span data-ttu-id="4368a-135">특성을 `ProviderManifestToken` 2005로 설정 하 고 SQL Server 버전이 2005 이지만 데이터베이스의 호환성 수준이 "80" (SQL Server 2000)로 설정 된 경우 생성 된 transact-sql은 SQL Server 2005를 대상으로 하지만 호환성 수준 설정으로 인해 예상 대로 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-135">If your `ProviderManifestToken` attribute is set to 2005 and your SQL Server version is 2005, but the compatibility level of a database is set to "80" (SQL Server 2000), the generated Transact-SQL will be targeting SQL Server 2005, but might not execute as expected due to the compatibility level setting.</span></span> <span data-ttu-id="4368a-136">예를 들어, ORDER BY 목록의 열 이름이 선택기의 열 이름과 일치하는 경우 정렬 정보가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-136">For example, you might lose ordering information if a column name in the ORDER BY list matches a column name in the selector.</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="4368a-137">프로젝션의 중첩 쿼리</span><span class="sxs-lookup"><span data-stu-id="4368a-137">Nested Queries in Projection</span></span>  

 <span data-ttu-id="4368a-138">프로젝션 절의 중첩 쿼리는 서버의 Cartesian 제품 쿼리로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-138">Nested queries in a projection clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="4368a-139">SQL Server를 포함 한 일부 백 엔드 서버에서는 TempDB 테이블이 매우 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-139">On some back-end servers, including SQL Server, this can cause the TempDB table to get quite large.</span></span> <span data-ttu-id="4368a-140">서버 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-140">This can decrease server performance.</span></span>  
  
 <span data-ttu-id="4368a-141">다음은 프로젝션 절의 중첩 쿼리 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-141">The following is an example of a nested query in a projection clause:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a><span data-ttu-id="4368a-142">서버에서 생성된 GUID ID 값</span><span class="sxs-lookup"><span data-stu-id="4368a-142">Server Generated GUID Identity Values</span></span>  

 <span data-ttu-id="4368a-143">Entity Framework는 서버에서 생성 된 GUID 형식 id 값을 지원 하지만, 공급자는 행이 삽입 된 후 서버에서 생성 된 id 값의 반환을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-143">The Entity Framework supports server-generated GUID type identity values, but the provider must support returning the server-generated identity value after a row was inserted.</span></span> <span data-ttu-id="4368a-144">SQL Server 2005부터 [OUTPUT 절](/sql/t-sql/queries/output-clause-transact-sql)을 통해 SQL Server 데이터베이스에서 서버에서 생성 된 GUID 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4368a-144">Starting with SQL Server 2005, you can return the server-generated GUID type in a SQL Server database through the [OUTPUT clause](/sql/t-sql/queries/output-clause-transact-sql).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4368a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4368a-145">See also</span></span>

- [<span data-ttu-id="4368a-146">Entity Framework용 SqlClient</span><span class="sxs-lookup"><span data-stu-id="4368a-146">SqlClient for the Entity Framework</span></span>](sqlclient-for-the-entity-framework.md)
- [<span data-ttu-id="4368a-147">LINQ to Entities에서 알려진 문제 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4368a-147">Known Issues and Considerations in LINQ to Entities</span></span>](./language-reference/known-issues-and-considerations-in-linq-to-entities.md)
