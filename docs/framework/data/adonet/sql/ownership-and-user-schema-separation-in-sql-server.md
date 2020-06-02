---
title: SQL Server에서 소유권 및 사용자와 스키마 분리
description: 사용자 스키마 분리를 통해 SQL Server 데이터베이스 개체 사용 권한 관리의 유연성을 활용 하는 방법을 알아봅니다. 스키마는 개체를 별도의 네임 스페이스로 그룹화 합니다.
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: 97e742979785fedd922dc887295b63e2d93bd147
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286264"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a><span data-ttu-id="faa6c-104">SQL Server에서 소유권 및 사용자와 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="faa6c-104">Ownership and User-Schema Separation in SQL Server</span></span>
<span data-ttu-id="faa6c-105">SQL Server 보안의 주요 개념은 개체 소유자에게 취소할 수 없는 개체 관리 권한이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-105">A core concept of SQL Server security is that owners of objects have irrevocable permissions to administer them.</span></span> <span data-ttu-id="faa6c-106">개체 소유자의 권한을 제거할 수 없으며 사용자가 데이터베이스의 개체를 소유하는 경우 데이터베이스에서 사용자를 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-106">You cannot remove privileges from an object owner, and you cannot drop users from a database if they own objects in it.</span></span>  
  
## <a name="user-schema-separation"></a><span data-ttu-id="faa6c-107">사용자 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="faa6c-107">User-Schema Separation</span></span>  
 <span data-ttu-id="faa6c-108">사용자 스키마 분리를 통해 데이터베이스 개체 권한을 더욱 유연하게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-108">User-schema separation allows for more flexibility in managing database object permissions.</span></span> <span data-ttu-id="faa6c-109">*스키마* 는 개체를 별도의 네임 스페이스로 그룹화 할 수 있도록 하는 데이터베이스 개체에 대 한 명명 된 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-109">A *schema* is a named container for database objects, which allows you to group objects into separate namespaces.</span></span> <span data-ttu-id="faa6c-110">예를 들어, AdventureWorks 샘플 데이터베이스에는 Production, Sales 및 HumanResources에 대한 스키마가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-110">For example, the AdventureWorks sample database contains schemas for Production, Sales, and HumanResources.</span></span>  
  
 <span data-ttu-id="faa6c-111">개체를 참조하는 4부분으로 구성된 명명 구문은 스키마 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-111">The four-part naming syntax for referring to objects specifies the schema name.</span></span>  
  
```text
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a><span data-ttu-id="faa6c-112">스키마 소유자 및 권한</span><span class="sxs-lookup"><span data-stu-id="faa6c-112">Schema Owners and Permissions</span></span>  
 <span data-ttu-id="faa6c-113">스키마는 데이터베이스 주체에서 소유하며 단일 주체가 여러 스키마를 소유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-113">Schemas can be owned by any database principal, and a single principal can own multiple schemas.</span></span> <span data-ttu-id="faa6c-114">스키마의 모든 개체에서 상속된 보안 규칙을 스키마에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-114">You can apply security rules to a schema, which are inherited by all objects in the schema.</span></span> <span data-ttu-id="faa6c-115">스키마에 대한 액세스 권한을 설정했으면 새 개체가 스키마에 추가되었으므로 이러한 권한이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-115">Once you set up access permissions for a schema, those permissions are automatically applied as new objects are added to the schema.</span></span> <span data-ttu-id="faa6c-116">사용자는 기본 스키마에 할당되며 여러 데이터베이스 사용자가 동일한 스키마를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-116">Users can be assigned a default schema, and multiple database users can share the same schema.</span></span>  
  
 <span data-ttu-id="faa6c-117">개발자가 스키마에서 개체를 만들 때 기본적으로 개발자가 아닌 스키마를 소유하는 보안 주체가 개체를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-117">By default, when developers create objects in a schema, the objects are owned by the security principal that owns the schema, not the developer.</span></span> <span data-ttu-id="faa6c-118">개체 소유권은 ALTER AUTHORIZATION Transact-SQL 문을 사용하여 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-118">Object ownership can be transferred with ALTER AUTHORIZATION Transact-SQL statement.</span></span> <span data-ttu-id="faa6c-119">스키마는 다른 사용자가 소유하고 스키마에 할당된 권한보다 세부적인 권한을 가지는 개체도 포함할 수 있지만 권한 관리가 복잡해지므로 이 방법은 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-119">A schema can also contain objects that are owned by different users and have more granular permissions than those assigned to the schema, although this is not recommended because it adds complexity to managing permissions.</span></span> <span data-ttu-id="faa6c-120">스키마 사이에 개체를 제거할 수 있으며 보안 주체 사이에 스키마 소유권을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-120">Objects can be moved between schemas, and schema ownership can be transferred between principals.</span></span> <span data-ttu-id="faa6c-121">스키마에 영향을 주지 않고 데이터베이스 사용자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-121">Database users can be dropped without affecting schemas.</span></span>  
  
### <a name="built-in-schemas"></a><span data-ttu-id="faa6c-122">기본 제공 스키마</span><span class="sxs-lookup"><span data-stu-id="faa6c-122">Built-In Schemas</span></span>  
 <span data-ttu-id="faa6c-123">SQL Server는 기본 제공 데이터베이스 사용자 및 역할과 같은 이름을 가진 10개의 미리 정의된 스키마와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-123">SQL Server ships with ten pre-defined schemas that have the same names as the built-in database users and roles.</span></span> <span data-ttu-id="faa6c-124">이 기능은 이전 버전과의 호환성을 위해 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-124">These exist mainly for backward compatibility.</span></span> <span data-ttu-id="faa6c-125">스키마가 필요하지 않은 경우 고정된 데이터베이스 역할과 이름이 같은 스키마를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-125">You can drop the schemas that have the same names as the fixed database roles if you do not need them.</span></span> <span data-ttu-id="faa6c-126">다음 스키마는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-126">You cannot drop the following schemas:</span></span>  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 <span data-ttu-id="faa6c-127">모델 데이터베이스에서 스키마를 삭제하면 해당 스키마가 새 데이터베이스에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-127">If you drop them from the model database, they will not appear in new databases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faa6c-128">`sys` 및 `INFORMATION_SCHEMA` 스키마는 시스템 개체용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-128">The `sys` and `INFORMATION_SCHEMA` schemas are reserved for system objects.</span></span> <span data-ttu-id="faa6c-129">이러한 스키마의 개체는 만들거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-129">You cannot create objects in these schemas and you cannot drop them.</span></span>  
  
#### <a name="the-dbo-schema"></a><span data-ttu-id="faa6c-130">dbo 스키마</span><span class="sxs-lookup"><span data-stu-id="faa6c-130">The dbo Schema</span></span>  
 <span data-ttu-id="faa6c-131">`dbo` 스키마는 새로 만든 데이터베이스의 기본 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-131">The `dbo` schema is the default schema for a newly created database.</span></span> <span data-ttu-id="faa6c-132">`dbo` 스키마는 `dbo` 사용자 계정에서 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-132">The `dbo` schema is owned by the `dbo` user account.</span></span> <span data-ttu-id="faa6c-133">CREATE USER Transact-SQL 명령을 사용하여 만들어진 사용자는 기본적으로 `dbo`를 기본 스키마로 가집니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-133">By default, users created with the CREATE USER Transact-SQL command have `dbo` as their default schema.</span></span>  
  
 <span data-ttu-id="faa6c-134">`dbo` 스키마에 할당된 사용자에게는 `dbo` 사용자 계정의 권한이 상속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-134">Users who are assigned the `dbo` schema do not inherit the permissions of the `dbo` user account.</span></span> <span data-ttu-id="faa6c-135">사용자에게는 스키마의 권한이 상속되지 않고 스키마에 포함된 데이터베이스 개체의 스키마 권한이 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-135">No permissions are inherited from a schema by users; schema permissions are inherited by the database objects contained in the schema.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faa6c-136">한 부분으로 구성된 이름을 사용하여 데이터베이스 개체를 참조할 때 SQL Server에서는 먼저 사용자의 기본 스키마를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-136">When database objects are referenced by using a one-part name, SQL Server first looks in the user's default schema.</span></span> <span data-ttu-id="faa6c-137">개체를 기본 스키마에서 찾을 수 없으면 SQL Server는 `dbo` 스키마에서 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-137">If the object is not found there, SQL Server looks next in the `dbo` schema.</span></span> <span data-ttu-id="faa6c-138">개체가 `dbo` 스키마에 없는 경우 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-138">If the object is not in the `dbo` schema, an error is returned.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="faa6c-139">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="faa6c-139">External Resources</span></span>  
 <span data-ttu-id="faa6c-140">개체 소유권 및 스키마에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faa6c-140">For more information on object ownership and schemas, see the following resources.</span></span>  
  
|<span data-ttu-id="faa6c-141">리소스</span><span class="sxs-lookup"><span data-stu-id="faa6c-141">Resource</span></span>|<span data-ttu-id="faa6c-142">Description</span><span class="sxs-lookup"><span data-stu-id="faa6c-142">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="faa6c-143">[사용자와 스키마 분리](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="faa6c-143">[User-Schema Separation](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span></span>|<span data-ttu-id="faa6c-144">사용자 스키마 분리에서 도입된 변경 내용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-144">Describes the changes introduced by user-schema separation.</span></span> <span data-ttu-id="faa6c-145">새 동작, 소유권에 대한 영향, 카탈로그 뷰 및 권한이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa6c-145">Includes new behavior, its impact on ownership, catalog views, and permissions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="faa6c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faa6c-146">See also</span></span>

- [<span data-ttu-id="faa6c-147">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="faa6c-147">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="faa6c-148">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="faa6c-148">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="faa6c-149">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="faa6c-149">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="faa6c-150">SQL Server의 서버 및 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="faa6c-150">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)
- [<span data-ttu-id="faa6c-151">SQL Server에서 권한 부여 및 권한</span><span class="sxs-lookup"><span data-stu-id="faa6c-151">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="faa6c-152">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="faa6c-152">ADO.NET Overview</span></span>](../ado-net-overview.md)
