---
description: '자세한 정보: 명령 실행'
title: 명령 실행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: 7b5fe46bf4d82fcd4f24cc0eb19e85a2ee9aca7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724325"
---
# <a name="executing-a-command"></a><span data-ttu-id="c7826-103">명령 실행</span><span class="sxs-lookup"><span data-stu-id="c7826-103">Executing a Command</span></span>

<span data-ttu-id="c7826-104">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbCommand>에서 상속되는 고유 명령 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-104">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="c7826-105">.NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbCommand> 개체가 있고, .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlCommand> 개체가 있으며, .NET Framework Data Provider for ODBC와 .NET Framework Data Provider for Oracle에는 각각 <xref:System.Data.Odbc.OdbcCommand> 개체와 <xref:System.Data.OracleClient.OracleCommand> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-105">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="c7826-106">이러한 각 개체는 명령의 유형 및 원하는 반환 값을 기준으로 명령 실행을 위한 메서드를 노출합니다. 다음 표에는 이러한 명령 및 해당 반환 값이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-106">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="c7826-107">명령</span><span class="sxs-lookup"><span data-stu-id="c7826-107">Command</span></span>|<span data-ttu-id="c7826-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7826-108">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="c7826-109">`DataReader` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-109">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="c7826-110">단일 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-110">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="c7826-111">어떠한 행도 반환하지 않는 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-111">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="c7826-112"><xref:System.Xml.XmlReader>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-112">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="c7826-113">`SqlCommand` 개체에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-113">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="c7826-114">강력한 형식의 각 명령 개체는 명령 문자열의 해석 방법을 지정하는 <xref:System.Data.CommandType> 열거형도 지원합니다. 다음 표에는 CommandType의 각 열거형이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-114">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="c7826-115">CommandType</span><span class="sxs-lookup"><span data-stu-id="c7826-115">CommandType</span></span>|<span data-ttu-id="c7826-116">설명</span><span class="sxs-lookup"><span data-stu-id="c7826-116">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="c7826-117">데이터 소스에 실행할 문을 정의하는 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-117">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="c7826-118">저장 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-118">The name of the stored procedure.</span></span> <span data-ttu-id="c7826-119">호출하는 `Parameters` 메서드에 관계없이 명령의 `Execute` 속성을 사용하면 입력 및 출력 매개 변수와 반환 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-119">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="c7826-120">`ExecuteReader`를 사용하는 경우 `DataReader`가 닫히기 전에는 반환 값과 출력 매개 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-120">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="c7826-121">테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-121">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c7826-122">예</span><span class="sxs-lookup"><span data-stu-id="c7826-122">Example</span></span>  

 <span data-ttu-id="c7826-123">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlCommand> 개체를 만든 다음 해당 속성을 설정하여 저장 프로시저를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-123">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="c7826-124">저장 프로시저에 대한 입력 매개 변수를 지정하는 데는 <xref:System.Data.SqlClient.SqlParameter> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-124">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="c7826-125"><xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 명령을 실행하고 <xref:System.Data.SqlClient.SqlDataReader>의 출력을 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-125">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="c7826-126">명령 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c7826-126">Troubleshooting Commands</span></span>  

 <span data-ttu-id="c7826-127">.NET Framework Data Provider for SQL Server는 실패한 명령 실행과 관련된 간헐적인 문제를 감지할 수 있도록 성능 카운터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7826-127">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="c7826-128">자세한 내용은 [성능 카운터](performance-counters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7826-128">For more information see [Performance Counters](performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7826-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7826-129">See also</span></span>

- [<span data-ttu-id="c7826-130">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7826-130">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="c7826-131">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="c7826-131">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c7826-132">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c7826-132">ADO.NET Overview</span></span>](ado-net-overview.md)
