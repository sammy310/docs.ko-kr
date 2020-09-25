---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: b5f2dbb687348afac98247cb21bae831dea26bfe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183314"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="e1d08-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="e1d08-102">DbProviderFactories</span></span>

<span data-ttu-id="e1d08-103"><xref:System.Data.Common> 네임스페이스에서는 특정 데이터 소스를 사용하기 위해 <xref:System.Data.Common.DbProviderFactory> 인스턴스를 만드는 데 필요한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="e1d08-104"><xref:System.Data.Common.DbProviderFactory> 인스턴스를 만든 다음 이 인스턴스에 데이터 공급자에 대한 정보를 전달하면 `DbProviderFactory`에서 제공된 정보에 따라 반환할 강력한 형식의 올바른 연결 개체를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="e1d08-105">.NET Framework 버전 4부터는 <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> 및 <xref:System.Data.OracleClient> 등의 데이터 공급자는 더 이상 제공되지 않지만 사용자 지정 공급자는 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1d08-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e1d08-106">In This Section</span></span>  

 [<span data-ttu-id="e1d08-107">팩터리 모델 개요</span><span class="sxs-lookup"><span data-stu-id="e1d08-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="e1d08-108">팩터리 디자인 패턴 및 프로그래밍 인터페이스를 간략히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="e1d08-109">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="e1d08-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="e1d08-110">설치된 데이터 공급자를 나열하고 <xref:System.Data.Common.DbConnection>에서 `DbProviderFactory`을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="e1d08-111">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="e1d08-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="e1d08-112"><xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbDataReader>를 만들고 <xref:System.Data.Common.DbException>을 사용하여 데이터 오류를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="e1d08-113">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="e1d08-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="e1d08-114"><xref:System.Data.Common.DbCommandBuilder>를 <xref:System.Data.Common.DbDataAdapter>와 함께 사용하여 데이터를 검색 및 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1d08-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d08-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1d08-115">See also</span></span>

- [<span data-ttu-id="e1d08-116">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="e1d08-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="e1d08-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="e1d08-117">ADO.NET Overview</span></span>](ado-net-overview.md)
