---
title: 네임스페이스(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: bef2fa96ce090a600155d68ecc3daea55b675840
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185525"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="2484f-102">네임스페이스(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2484f-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2484f-103">형식 이름, 엔터티 집합, 함수 등의 전역 식별자에 대 한 이름 충돌을 피하기 위해 네임 스페이스를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-103">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="2484f-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 네임스페이스 지원은 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]의 네임스페이스 지원과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2484f-105">두 가지 형태의 USING 절을 제공 합니다: 다음 예제의 그림과 같이 (여기서는 짧은 별칭이 제공 됨 네임 스페이스에 대 한) 네임 스페이스 및 정규화 된 네임 스페이스를 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-105">provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="2484f-106">이름 확인 규칙</span><span class="sxs-lookup"><span data-stu-id="2484f-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="2484f-107">식별자를 로컬 범위에서 확인할 수 없는 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 전역 범위 (네임 스페이스)에서 이름을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2484f-108">먼저 정규화 된 네임 스페이스 중 하나를 사용 하 여 식별자 (접두사)와 일치 하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="2484f-109">일치하는 것이 있으면 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 해당 네임스페이스에서 나머지 식별자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="2484f-110">일치하는 것이 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="2484f-111">다음으로 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 모든 비정규화된 네임스페이스(프롤로그에 지정됨)에서 식별자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="2484f-112">식별자를 정확하게 하나의 네임스페이스에서 찾을 수 있으면 해당 위치가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="2484f-113">해당 식별자와 일치하는 네임스페이스가 둘 이상이면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="2484f-114">식별자의 네임스페이스를 확인할 수 없는 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 다음 예제와 같이 이름을 다음 바깥쪽 범위(<xref:System.Data.Common.DbCommand> 또는 <xref:System.Data.Common.DbConnection> 개체)로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="2484f-115">.NET Framework와의 차이점</span><span class="sxs-lookup"><span data-stu-id="2484f-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="2484f-116">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]에서는 부분적으로 정규화된 네임스페이스를 사용할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="2484f-116">In the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="2484f-117">이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="2484f-118">ADO.NET 사용</span><span class="sxs-lookup"><span data-stu-id="2484f-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="2484f-119">쿼리는 ADO.NET <xref:System.Data.Common.DbCommand> 개체를 통해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <xref:System.Data.Common.DbCommand> <span data-ttu-id="2484f-120">통해 개체를 빌드할 수 있습니다 <xref:System.Data.Common.DbConnection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-120">objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="2484f-121">네임스페이스는 <xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbConnection> 개체의 일부로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2484f-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="2484f-122">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 쿼리 자체 내에서 식별자를 확인할 수 없는 경우 외부 네임스페이스를 검색합니다(비슷한 규칙이 사용됨).</span><span class="sxs-lookup"><span data-stu-id="2484f-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2484f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="2484f-123">See also</span></span>

- [<span data-ttu-id="2484f-124">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="2484f-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="2484f-125">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="2484f-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
