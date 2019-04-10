---
title: Entity Framework용 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: d81499961e7e47bba3b2594ddddd192c87a4a936
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195464"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="6da51-102">Entity Framework용 SqlClient</span><span class="sxs-lookup"><span data-stu-id="6da51-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="6da51-103">이 단원에서는 Entity Framework가 Microsoft SQL Server에서 작동할 수 있도록 하는 .NET Framework Data Provider for SQL Server(SqlClient)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="6da51-104">공급자 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="6da51-104">Provider Schema Attribute</span></span>  
 `Provider` <span data-ttu-id="6da51-105">특성을 `Schema` 요소 (SSDL) 저장소 스키마 정의 언어에서입니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-105">is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="6da51-106">SqlClient를 사용하려면 `Provider` 요소의 `Schema` 특성에 "System.Data.SqlClient" 문자열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="6da51-107">ProviderManifestToken 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="6da51-107">ProviderManifestToken Schema Attribute</span></span>  
 `ProviderManifestToken` <span data-ttu-id="6da51-108">필수 특성을 `Schema` ssdl에서 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-108">is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="6da51-109">이 토큰은 오프라인 시나리오용으로 공급자 매니페스트를 로드하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="6da51-110">에 대 한 자세한 내용은 `ProviderManifestToken` 특성을 참조 하십시오 [스키마 요소 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="6da51-111">SqlClient 다른 버전의 SQL Server에 대 한 데이터 공급자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="6da51-112">이러한 버전에는 서로 다른 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-112">These versions have different capabilities.</span></span> <span data-ttu-id="6da51-113">예를 들어 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]은 `varchar(max)`에서 도입된 `nvarchar(max)` 및 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="6da51-114">SqlClient는 여러 버전의 SQL Server에 대해 다음과 같은 공급자 매니페스트 토큰을 생성하고 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="6da51-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="6da51-115">SQL Server 2000</span></span>|<span data-ttu-id="6da51-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="6da51-116">SQL Server 2005</span></span>|<span data-ttu-id="6da51-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="6da51-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="6da51-118">2000</span><span class="sxs-lookup"><span data-stu-id="6da51-118">2000</span></span>|<span data-ttu-id="6da51-119">2005</span><span class="sxs-lookup"><span data-stu-id="6da51-119">2005</span></span>|<span data-ttu-id="6da51-120">2008</span><span class="sxs-lookup"><span data-stu-id="6da51-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6da51-121">Visual Studio 2010을 사용 하 여 시작 합니다 [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) SQL Server 2000을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-121">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="6da51-122">공급자 네임스페이스 이름</span><span class="sxs-lookup"><span data-stu-id="6da51-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="6da51-123">모든 공급자에서 네임스페이스가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-123">All providers must specify a namespace.</span></span> <span data-ttu-id="6da51-124">이 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자에서 사용할 수 있는 접두사를 Entity Framework에서 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="6da51-125">SqlClient 공급자 매니페스트의 네임스페이스는 `SqlServer`입니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="6da51-126">네임 스페이스에 대 한 자세한 내용은 참조 하세요. [네임 스페이스](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="6da51-127">유형</span><span class="sxs-lookup"><span data-stu-id="6da51-127">Types</span></span>  
 <span data-ttu-id="6da51-128">Entity Framework에 대한 SqlClient 공급자는 개념적 모델 형식과 SQL Server 형식 간의 매핑 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="6da51-129">자세한 내용은 [Entity FrameworkTypes 용 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="6da51-130">함수</span><span class="sxs-lookup"><span data-stu-id="6da51-130">Functions</span></span>  
 <span data-ttu-id="6da51-131">Entity Framework에 대한 SqlClient 공급자는 해당 공급자가 지원하는 함수 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="6da51-132">지원 되는 함수의 목록을 참조 하세요 [Entity Framework 함수에 대 한 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6da51-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6da51-133">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6da51-133">In This Section</span></span>  
 [<span data-ttu-id="6da51-134">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="6da51-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="6da51-135">Entity FrameworkTypes용 SqlClient</span><span class="sxs-lookup"><span data-stu-id="6da51-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="6da51-136">Entity Framework용 SqlClient에서 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="6da51-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="6da51-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="6da51-137">See also</span></span>

- [<span data-ttu-id="6da51-138">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="6da51-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="6da51-139">언어 참조</span><span class="sxs-lookup"><span data-stu-id="6da51-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [<span data-ttu-id="6da51-140">Entity Framework 용 SqlClient 공급자의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="6da51-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
