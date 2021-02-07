---
description: '자세히 알아보기: Entity Framework의 SqlClient'
title: Entity Framework용 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: eba5602c13f66d1ee4404bbc27035304e34c1cd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673130"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="8b6fd-103">Entity Framework용 SqlClient</span><span class="sxs-lookup"><span data-stu-id="8b6fd-103">SqlClient for the Entity Framework</span></span>

<span data-ttu-id="8b6fd-104">이 단원에서는 Entity Framework가 Microsoft SQL Server에서 작동할 수 있도록 하는 .NET Framework Data Provider for SQL Server(SqlClient)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-104">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="8b6fd-105">공급자 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="8b6fd-105">Provider Schema Attribute</span></span>  

 <span data-ttu-id="8b6fd-106">`Provider`는 SSDL(저장소 스키마 정의 언어)의 `Schema` 요소에 대한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-106">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="8b6fd-107">SqlClient를 사용하려면 `Provider` 요소의 `Schema` 특성에 "System.Data.SqlClient" 문자열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-107">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="8b6fd-108">ProviderManifestToken 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="8b6fd-108">ProviderManifestToken Schema Attribute</span></span>  

 <span data-ttu-id="8b6fd-109">`ProviderManifestToken`은 SSDL에서 `Schema` 요소의 필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-109">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="8b6fd-110">이 토큰은 오프라인 시나리오용으로 공급자 매니페스트를 로드하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-110">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="8b6fd-111">특성에 대 한 자세한 내용은 `ProviderManifestToken` [Schema 요소 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-111">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="8b6fd-112">SqlClient는 여러 버전의 SQL Server에 대 한 데이터 공급자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-112">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="8b6fd-113">이러한 버전에는 서로 다른 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-113">These versions have different capabilities.</span></span> <span data-ttu-id="8b6fd-114">예를 들어 SQL Server 2000는 `varchar(max)` SQL Server 2005에서 도입 된 및 형식을 지원 하지 않습니다 `nvarchar(max)` .</span><span class="sxs-lookup"><span data-stu-id="8b6fd-114">For example, SQL Server 2000 does not support `varchar(max)` and `nvarchar(max)` types that were introduced with SQL Server 2005.</span></span>  
  
 <span data-ttu-id="8b6fd-115">SqlClient는 여러 버전의 SQL Server에 대해 다음과 같은 공급자 매니페스트 토큰을 생성하고 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-115">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="8b6fd-116">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="8b6fd-116">SQL Server 2000</span></span>|<span data-ttu-id="8b6fd-117">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="8b6fd-117">SQL Server 2005</span></span>|<span data-ttu-id="8b6fd-118">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="8b6fd-118">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="8b6fd-119">2000</span><span class="sxs-lookup"><span data-stu-id="8b6fd-119">2000</span></span>|<span data-ttu-id="8b6fd-120">2005</span><span class="sxs-lookup"><span data-stu-id="8b6fd-120">2005</span></span>|<span data-ttu-id="8b6fd-121">2008</span><span class="sxs-lookup"><span data-stu-id="8b6fd-121">2008</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8b6fd-122">Visual Studio 2010부터 [ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) 는 SQL Server 2000를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-122">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="8b6fd-123">공급자 네임스페이스 이름</span><span class="sxs-lookup"><span data-stu-id="8b6fd-123">Provider Namespace Name</span></span>  

 <span data-ttu-id="8b6fd-124">모든 공급자에서 네임스페이스가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-124">All providers must specify a namespace.</span></span> <span data-ttu-id="8b6fd-125">이 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자에서 사용할 수 있는 접두사를 Entity Framework에서 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-125">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="8b6fd-126">SqlClient 공급자 매니페스트의 네임스페이스는 `SqlServer`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-126">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="8b6fd-127">네임 스페이스에 대 한 자세한 내용은 [네임 스페이스](./language-reference/namespaces-entity-sql.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-127">For more information about namespaces, see [Namespaces](./language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="8b6fd-128">형식</span><span class="sxs-lookup"><span data-stu-id="8b6fd-128">Types</span></span>  

 <span data-ttu-id="8b6fd-129">Entity Framework에 대한 SqlClient 공급자는 개념적 모델 형식과 SQL Server 형식 간의 매핑 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-129">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="8b6fd-130">자세한 내용은 [Entity frameworktypes 용 sqlclient의 SqlClient](sqlclient-for-ef-types.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-130">For more information, see [SqlClient for Entity FrameworkTypes](sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="8b6fd-131">Functions</span><span class="sxs-lookup"><span data-stu-id="8b6fd-131">Functions</span></span>  

 <span data-ttu-id="8b6fd-132">Entity Framework에 대한 SqlClient 공급자는 해당 공급자가 지원하는 함수 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-132">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="8b6fd-133">지원 되는 함수 목록은 [Entity Framework 함수에 대 한 SqlClient](sqlclient-for-ef-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6fd-133">For a list of the supported functions, see [SqlClient for Entity Framework Functions](sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b6fd-134">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8b6fd-134">In This Section</span></span>  

 [<span data-ttu-id="8b6fd-135">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="8b6fd-135">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="8b6fd-136">Entity FrameworkTypes용 SqlClient</span><span class="sxs-lookup"><span data-stu-id="8b6fd-136">SqlClient for Entity FrameworkTypes</span></span>](sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="8b6fd-137">Entity Framework용 SqlClient에서 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="8b6fd-137">Known Issues in SqlClient for Entity Framework</span></span>](known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b6fd-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b6fd-138">See also</span></span>

- [<span data-ttu-id="8b6fd-139">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="8b6fd-139">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="8b6fd-140">언어 참조</span><span class="sxs-lookup"><span data-stu-id="8b6fd-140">Language Reference</span></span>](./language-reference/index.md)
- [<span data-ttu-id="8b6fd-141">Entity Framework에 대 한 SqlClient 공급자의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="8b6fd-141">Known Issues in SqlClient Provider for Entity Framework</span></span>](sqlclient-for-the-entity-framework.md)
