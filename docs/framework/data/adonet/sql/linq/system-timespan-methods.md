---
description: '자세한 정보: 시스템 TimeSpan 메서드'
title: System.TimeSpan 메서드
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: fa3192d18a59e589f2c7510776f8510b2c12cac4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681190"
---
# <a name="systemtimespan-methods"></a><span data-ttu-id="8fe9a-103">System.TimeSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="8fe9a-103">System.TimeSpan Methods</span></span>

<span data-ttu-id="8fe9a-104"><xref:System.TimeSpan?displayProperty=nameWithType>에 대한 멤버 지원은 사용 중인 .NET Framework 및 Microsoft SQL Server의 버전에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-104">Member support for <xref:System.TimeSpan?displayProperty=nameWithType> greatly depends on the versions of the .NET Framework and Microsoft SQL Server that you are using.</span></span>  
  
 <span data-ttu-id="8fe9a-105">메서드, 연산자 또는 속성이 지원되지 않는 경우 LINQ to SQL에서는 멤버를 SQL Server에서 실행하기 위해 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-105">When a method, operator, or property is unsupported; it means that LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="8fe9a-106">이러한 멤버를 코드에 사용할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="8fe9a-106">You may still be able to use these members in your code.</span></span> <span data-ttu-id="8fe9a-107">쿼리를 Transact-SQL로 변환하기 전이나 데이터베이스에서 결과가 검색된 후에 반드시 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-107">However, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="previous-limitations"></a><span data-ttu-id="8fe9a-108">기존의 제한</span><span class="sxs-lookup"><span data-stu-id="8fe9a-108">Previous Limitations</span></span>  

 <span data-ttu-id="8fe9a-109">.NET Framework 3.5 SP1보다 낮은 버전의 .NET Framework과 함께 LINQ to SQL을 사용하는 경우 SQL Server 데이터베이스 필드를 <xref:System.TimeSpan?displayProperty=nameWithType>에 매핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-109">When using LINQ to SQL with versions of the .NET Framework prior to .NET Framework 3.5 SP1, you cannot map SQL Server database fields to <xref:System.TimeSpan?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8fe9a-110">그러나 <xref:System.TimeSpan> 값은 <xref:System.TimeSpan> 빼기에서 반환되거나 리터럴 또는 바인딩된 변수로 식에 삽입될 수 있기 때문에 <xref:System.DateTime>에 대한 연산은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-110">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
## <a name="supported-systemtimespan-member-support"></a><span data-ttu-id="8fe9a-111">지원 되는 시스템. TimeSpan 멤버 지원</span><span class="sxs-lookup"><span data-stu-id="8fe9a-111">Supported System.TimeSpan member support</span></span>

 <span data-ttu-id="8fe9a-112">다음 LINQ to SQL에서 지원하는 메서드, 연산자 및 속성을 LINQ to SQL 쿼리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-112">The following LINQ to SQL-supported methods, operators, and properties are available for you to use in your LINQ to SQL queries.</span></span> <span data-ttu-id="8fe9a-113">개체 모델 또는 외부 매핑 파일에 매핑되면 LINQ to SQL을 사용하여 LINQ to SQL 쿼리 내부의 <xref:System.TimeSpan?displayProperty=nameWithType> 멤버 대부분을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-113">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call many of the <xref:System.TimeSpan?displayProperty=nameWithType> members inside your LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="8fe9a-114">지원되는 <xref:System.TimeSpan> 메서드</span><span class="sxs-lookup"><span data-stu-id="8fe9a-114">Supported <xref:System.TimeSpan> Methods</span></span>|<span data-ttu-id="8fe9a-115">지원되는 <xref:System.TimeSpan> 연산자</span><span class="sxs-lookup"><span data-stu-id="8fe9a-115">Supported <xref:System.TimeSpan> Operators</span></span>|<span data-ttu-id="8fe9a-116">지원되는 <xref:System.TimeSpan> 속성</span><span class="sxs-lookup"><span data-stu-id="8fe9a-116">Supported <xref:System.TimeSpan> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
> <span data-ttu-id="8fe9a-117">LINQ to SQL을 사용하여 <xref:System.TimeSpan?displayProperty=nameWithType>을 SQL `TIME` 열에 매핑하려면 .NET Framework 3.5 SP1 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-117">The ability to map <xref:System.TimeSpan?displayProperty=nameWithType> to a SQL `TIME` column with LINQ to SQL requires the .NET Framework 3.5 SP1 and beyond.</span></span> <span data-ttu-id="8fe9a-118">SQL `TIME` 데이터 형식은 Microsoft SQL Server 2008 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-118">The SQL `TIME` data type is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
### <a name="addition-and-subtraction"></a><span data-ttu-id="8fe9a-119">더하기 및 빼기</span><span class="sxs-lookup"><span data-stu-id="8fe9a-119">Addition and Subtraction</span></span>  

 <span data-ttu-id="8fe9a-120">CLR <xref:System.TimeSpan?displayProperty=nameWithType> 형식은 더하기와 빼기를 지원하지만 SQL `TIME` 형식은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-120">Although the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type does support addition and subtraction, the SQL `TIME` type does not.</span></span> <span data-ttu-id="8fe9a-121">이 때문에 LINQ to SQL 쿼리에서 SQL `TIME` 형식에 매핑할 때 더하기와 빼기를 시도할 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-121">Because of this, your LINQ to SQL queries will generate errors if they attempt addition and subtraction when they are mapped to the SQL `TIME` type.</span></span> <span data-ttu-id="8fe9a-122">Sql의 날짜 및 시간 형식에 대 한 작업에 대 한 기타 고려 사항은 [SQL CLR 형식 매핑에서](sql-clr-type-mapping.md)확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fe9a-122">You can find other considerations for working with SQL date and time types in [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe9a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fe9a-123">See also</span></span>

- [<span data-ttu-id="8fe9a-124">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="8fe9a-124">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="8fe9a-125">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="8fe9a-125">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="8fe9a-126">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="8fe9a-126">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="8fe9a-127">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="8fe9a-127">Data Types and Functions</span></span>](data-types-and-functions.md)
