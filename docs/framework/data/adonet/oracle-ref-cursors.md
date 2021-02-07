---
description: '자세한 정보: Oracle REF Cursor'
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 0a9c5e95a9f0d2da74fd6a3db19f15699a3e2787
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672454"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="9534b-103">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="9534b-103">Oracle REF CURSORs</span></span>

<span data-ttu-id="9534b-104">Oracle의 .NET Framework Data Provider는 Oracle **REF CURSOR** 데이터 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-104">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="9534b-105">Oracle REF CURSOR를 사용하는 데이터 공급자를 사용할 경우 다음 동작을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-105">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9534b-106">일부 동작이 MSDAORA(Microsoft OLE DB Provider for Oracle)의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-106">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="9534b-107">성능상의 이유로 Oracle의 Data Provider는 명시적으로 지정 하지 않는 한 MSDAORA 처럼 **REF CURSOR** 데이터 형식을 자동으로 바인딩하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-107">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="9534b-108">데이터 공급자는 REF CURSOR 매개 변수를 지정하는 데 사용되는 {resultset} 이스케이프를 포함하여 ODBC 이스케이프 시퀀스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-108">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="9534b-109">REF Cursor를 반환 하는 저장 프로시저를 실행 하려면 <xref:System.Data.OracleClient.OracleParameterCollection> <xref:System.Data.OracleClient.OracleType> **커서** 와 <xref:System.Data.OracleClient.OracleParameter.Direction%2A> **출력** 의를 사용 하 여에 매개 변수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-109">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="9534b-110">데이터 공급자는 REF CURSOR를 출력 매개 변수로만 바인딩하는 것을 지원하며</span><span class="sxs-lookup"><span data-stu-id="9534b-110">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="9534b-111">REF CURSOR를 입력 매개 변수로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-111">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="9534b-112">매개 변수 값에서 <xref:System.Data.OracleClient.OracleDataReader>를 가져오는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-112">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="9534b-113">값의 형식은 명령이 실행된 후의 <xref:System.DBNull>입니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-113">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="9534b-114">REF 커서를 사용 하는 경우 (예:를 호출 하는 경우)에만 **CommandBehavior** 열거형 값 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 이 **CloseConnection**, 다른 모든 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-114">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="9534b-115">**OracleDataReader** 에서 참조 커서의 순서는 **OracleParameterCollection** 의 매개 변수 순서에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-115">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="9534b-116"><xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-116">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="9534b-117">PL/SQL **테이블** 데이터 형식은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-117">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="9534b-118">그러나 REF CURSOR가 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-118">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="9534b-119">**테이블** 데이터 형식을 사용 해야 하는 경우 MSDAORA와 함께 OLE DB .net Data Provider를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-119">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9534b-120">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9534b-120">In This Section</span></span>  

 [<span data-ttu-id="9534b-121">REF CURSOR 예제</span><span class="sxs-lookup"><span data-stu-id="9534b-121">REF CURSOR Examples</span></span>](ref-cursor-examples.md)  
 <span data-ttu-id="9534b-122">REF CURSOR의 사용을 보여 주는 세 가지 예제가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-122">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="9534b-123">OracleDataReader의 REF CURSOR 매개 변수</span><span class="sxs-lookup"><span data-stu-id="9534b-123">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="9534b-124">REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하 고 값을 **OracleDataReader** 로 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-124">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="9534b-125">OracleDataReader를 사용하여 여러 Multiple REF CURSOR에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="9534b-125">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="9534b-126">두 개의 REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하 고 **OracleDataReader** 를 사용 하 여 값을 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-126">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="9534b-127">하나 이상의 REF CURSOR를 사용하여 데이터 세트 필터링</span><span class="sxs-lookup"><span data-stu-id="9534b-127">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="9534b-128">두 개의 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하여 반환되는 행으로 <xref:System.Data.DataSet>을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9534b-128">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9534b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9534b-129">See also</span></span>

- [<span data-ttu-id="9534b-130">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9534b-130">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="9534b-131">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="9534b-131">ADO.NET Overview</span></span>](ado-net-overview.md)
