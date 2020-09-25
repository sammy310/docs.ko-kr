---
title: SQL Server의 서버 및 데이터베이스 역할
description: 고정 된 권한 집합이 할당 된 고정 서버 및 고정 데이터베이스 역할에 대해 알아봅니다. SQL Server는 역할 기반 보안을 사용 합니다.
ms.date: 03/30/2017
ms.assetid: 5482dfdb-e498-4614-8652-b174829eed13
ms.openlocfilehash: 3babf6b249da6e67a6a48bcad647e4674650c348
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177334"
---
# <a name="server-and-database-roles-in-sql-server"></a><span data-ttu-id="1fbd7-104">SQL Server의 서버 및 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-104">Server and Database Roles in SQL Server</span></span>

<span data-ttu-id="1fbd7-105">모든 버전의 SQL Server에서는 역할 기반 보안을 사용하므로 개별 사용자 대신 역할이나 사용자 그룹에 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-105">All versions of SQL Server use role-based security, which allows you to assign permissions to a role, or group of users, instead of to individual users.</span></span> <span data-ttu-id="1fbd7-106">고정 서버 역할과 고정 데이터베이스 역할에는 고정 권한 집합이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-106">Fixed server and fixed database roles have a fixed set of permissions assigned to them.</span></span>  
  
## <a name="fixed-server-roles"></a><span data-ttu-id="1fbd7-107">고정 서버 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-107">Fixed Server Roles</span></span>  

 <span data-ttu-id="1fbd7-108">고정 서버 역할에는 서버 범위의 고정 권한 집합이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-108">Fixed server roles have a fixed set of permissions and server-wide scope.</span></span> <span data-ttu-id="1fbd7-109">고정 서버 역할은 SQL Server를 관리하는 데 사용되며 이 역할에 할당된 권한은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-109">They are intended for use in administering SQL Server and the permissions assigned to them cannot be changed.</span></span> <span data-ttu-id="1fbd7-110">데이터베이스에 사용자 계정을 만들지 않고도 고정 서버 역할에 로그인을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-110">Logins can be assigned to fixed server roles without having a user account in a database.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1fbd7-111">`sysadmin` 고정 서버 역할은 다른 모든 역할을 포함하며 범위에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-111">The `sysadmin` fixed server role encompasses all other roles and has unlimited scope.</span></span> <span data-ttu-id="1fbd7-112">완전히 신뢰할 수 있는 보안 주체만 이 역할에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-112">Do not add principals to this role unless they are highly trusted.</span></span> <span data-ttu-id="1fbd7-113">`sysadmin` 역할 멤버는 모든 서버 데이터베이스 및 리소스에 대해 취소할 수 없는 관리 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-113">`sysadmin` role members have irrevocable administrative privileges on all server databases and resources.</span></span>  
  
 <span data-ttu-id="1fbd7-114">고정 서버 역할에 사용자를 추가할 때는 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-114">Be selective when you add users to fixed server roles.</span></span> <span data-ttu-id="1fbd7-115">예를 들어 `bulkadmin` 역할에 속한 사용자는 로컬 파일의 내용을 테이블에 삽입할 수 있으므로 이로 인해 데이터 무결성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-115">For example, the `bulkadmin` role allows users to insert the contents of any local file into a table, which could jeopardize data integrity.</span></span> <span data-ttu-id="1fbd7-116">고정 서버 역할 및 권한의 전체 목록은 SQL Server 온라인 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-116">See SQL Server Books Online for the complete list of fixed server roles and permissions.</span></span>  
  
## <a name="fixed-database-roles"></a><span data-ttu-id="1fbd7-117">고정 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-117">Fixed Database Roles</span></span>  

 <span data-ttu-id="1fbd7-118">고정 데이터베이스 역할에는 권한 그룹을 간편하게 관리할 수 있도록 미리 정의된 권한 집합이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-118">Fixed database roles have a pre-defined set of permissions that are designed to allow you to easily manage groups of permissions.</span></span> <span data-ttu-id="1fbd7-119">`db_owner` 역할의 멤버는 데이터베이스에 대한 모든 구성 및 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-119">Members of the `db_owner` role can perform all configuration and maintenance activities on the database.</span></span>  
  
 <span data-ttu-id="1fbd7-120">SQL Server의 미리 정의된 역할에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-120">For more information about SQL Server predefined roles, see the following resources.</span></span>  
  
|<span data-ttu-id="1fbd7-121">리소스</span><span class="sxs-lookup"><span data-stu-id="1fbd7-121">Resource</span></span>|<span data-ttu-id="1fbd7-122">설명</span><span class="sxs-lookup"><span data-stu-id="1fbd7-122">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="1fbd7-123">서버 수준 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-123">Server-Level Roles</span></span>](/sql/relational-databases/security/authentication-access/server-level-roles)|<span data-ttu-id="1fbd7-124">SQL Server에서 고정 서버 역할 및 이와 관련 된 사용 권한을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-124">Describes fixed server roles and the permissions associated with them in SQL Server.</span></span>|  
|[<span data-ttu-id="1fbd7-125">데이터베이스 수준 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-125">Database-Level Roles</span></span>](/sql/relational-databases/security/authentication-access/database-level-roles)|<span data-ttu-id="1fbd7-126">고정 데이터베이스 역할 및 역할에 연결된 권한에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-126">Describes fixed database roles and the permissions associated with them</span></span>|  
  
## <a name="database-roles-and-users"></a><span data-ttu-id="1fbd7-127">데이터베이스 역할 및 사용자</span><span class="sxs-lookup"><span data-stu-id="1fbd7-127">Database Roles and Users</span></span>  

 <span data-ttu-id="1fbd7-128">데이터베이스 개체를 사용하려면 로그인을 데이터베이스 사용자 계정에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-128">Logins must be mapped to database user accounts in order to work with database objects.</span></span> <span data-ttu-id="1fbd7-129">그러면 데이터베이스 사용자를 데이터베이스 역할에 추가하여 해당 역할에 연결된 모든 권한을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-129">Database users can then be added to database roles, inheriting any permission sets associated with those roles.</span></span> <span data-ttu-id="1fbd7-130">모든 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-130">All permissions can be granted.</span></span>  
  
 <span data-ttu-id="1fbd7-131">애플리케이션 보안을 디자인할 때 `public` 역할, `dbo` 사용자 계정 및 `guest` 계정에 대해 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-131">You must also consider the `public` role, the `dbo` user account, and the `guest` account when you design security for your application.</span></span>  
  
### <a name="the-public-role"></a><span data-ttu-id="1fbd7-132">public 역할</span><span class="sxs-lookup"><span data-stu-id="1fbd7-132">The public Role</span></span>  

 <span data-ttu-id="1fbd7-133">`public` 역할은 시스템 데이터베이스를 비롯한 모든 데이터베이스에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-133">The `public` role is contained in every database, which includes system databases.</span></span> <span data-ttu-id="1fbd7-134">이 역할은 삭제할 수 없으며 이 역할에서 사용자를 추가 또는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-134">It cannot be dropped and you cannot add or remove users from it.</span></span> <span data-ttu-id="1fbd7-135">모든 사용자 및 역할은 기본적으로 `public` 역할에 속하므로 `public` 역할에 부여된 권한을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-135">Permissions granted to the `public` role are inherited by all other users and roles because they belong to the `public` role by default.</span></span> <span data-ttu-id="1fbd7-136">따라서 모든 사용자에게 허용하려는 권한만 `public` 역할에 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-136">Grant `public` only the permissions you want all users to have.</span></span>  
  
### <a name="the-dbo-user-account"></a><span data-ttu-id="1fbd7-137">dbo 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="1fbd7-137">The dbo User Account</span></span>  

 <span data-ttu-id="1fbd7-138">`dbo` 또는 데이터베이스 소유자는 데이터베이스에서 모든 작업을 수행할 수 있는 권한을 암시적으로 가지고 있는 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-138">The `dbo`, or database owner, is a user account that has implied permissions to perform all activities in the database.</span></span> <span data-ttu-id="1fbd7-139">`sysadmin` 고정 서버 역할의 멤버는 자동으로 `dbo`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-139">Members of the `sysadmin` fixed server role are automatically mapped to `dbo`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fbd7-140">`dbo` 는 [SQL Server의 소유권 및 사용자 스키마 분리](ownership-and-user-schema-separation-in-sql-server.md)에 설명 된 스키마의 이름 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-140">`dbo` is also the name of a schema, as discussed in [Ownership and User-Schema Separation in SQL Server](ownership-and-user-schema-separation-in-sql-server.md).</span></span>  
  
 <span data-ttu-id="1fbd7-141">`dbo` 사용자 계정을 `db_owner` 고정 데이터베이스 역할과 혼동하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-141">The `dbo` user account is frequently confused with the `db_owner` fixed database role.</span></span> <span data-ttu-id="1fbd7-142">`db_owner`의 범위는 데이터베이스이고 `sysadmin`의 범위는 전체 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-142">The scope of `db_owner` is a database; the scope of `sysadmin` is the whole server.</span></span> <span data-ttu-id="1fbd7-143">`db_owner` 역할의 멤버 자격은 `dbo` 사용자 권한을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-143">Membership in the `db_owner` role does not confer `dbo` user privileges.</span></span>  
  
### <a name="the-guest-user-account"></a><span data-ttu-id="1fbd7-144">guest 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="1fbd7-144">The guest User Account</span></span>  

 <span data-ttu-id="1fbd7-145">사용자가 인증되어 SQL Server 인스턴스에 로그인할 수 있게 된 경우 해당 사용자가 액세스하는 각 데이터베이스에는 별도의 사용자 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-145">After a user has been authenticated and allowed to log in to an instance of SQL Server, a separate user account must exist in each database the user has to access.</span></span> <span data-ttu-id="1fbd7-146">각 데이터베이스에 사용자 계정이 있어야 하므로 사용자가 SQL Server의 한 인스턴스에 연결한 후 서버의 모든 데이터베이스에 액세스하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-146">Requiring a user account in each database prevents users from connecting to an instance of SQL Server and accessing all the databases on a server.</span></span> <span data-ttu-id="1fbd7-147">데이터베이스에 `guest` 사용자 계정이 있으므로 로그인한 계정은 데이터베이스 사용자 계정이 없어도 데이터베이스에 액세스함으로써 이러한 요구 사항을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-147">The existence of a `guest` user account in the database circumvents this requirement by allowing a login without a database user account to access a database.</span></span>  
  
 <span data-ttu-id="1fbd7-148">`guest` 계정은 모든 버전의 SQL Server에 포함된 기본 제공 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-148">The `guest` account is a built-in account in all versions of SQL Server.</span></span> <span data-ttu-id="1fbd7-149">새 데이터베이스에서는 이 계정이 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-149">By default, it is disabled in new databases.</span></span> <span data-ttu-id="1fbd7-150">이 계정이 활성화되어 있는 경우 Transact-SQL의 REVOKE CONNECT FROM GUEST 문을 실행하여 계정의 CONNECT 권한을 취소함으로써 이 계정을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-150">If it is enabled, you can disable it by revoking its CONNECT permission by executing the Transact-SQL REVOKE CONNECT FROM GUEST statement.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1fbd7-151">고유 데이터베이스 권한이 없는 모든 로그인은 이 계정에 부여된 데이터베이스 권한을 가지게 되므로 `guest` 계정은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-151">Avoid using the `guest` account; all logins without their own database permissions obtain the database permissions granted to this account.</span></span> <span data-ttu-id="1fbd7-152">불가피하게 `guest` 계정을 사용해야 하는 경우에는 계정에 최소 권한만 부여하세요.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-152">If you must use the `guest` account, grant it minimum permissions.</span></span>  
  
 <span data-ttu-id="1fbd7-153">SQL Server 로그인, 사용자 및 역할에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-153">For more information about SQL Server logins, users and roles, see the following resources.</span></span>  
  
|<span data-ttu-id="1fbd7-154">리소스</span><span class="sxs-lookup"><span data-stu-id="1fbd7-154">Resource</span></span>|<span data-ttu-id="1fbd7-155">설명</span><span class="sxs-lookup"><span data-stu-id="1fbd7-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="1fbd7-156">데이터베이스 엔진 권한 시작</span><span class="sxs-lookup"><span data-stu-id="1fbd7-156">Getting Started with Database Engine Permissions</span></span>](/sql/relational-databases/security/authentication-access/getting-started-with-database-engine-permissions)|<span data-ttu-id="1fbd7-157">보안 주체, 역할, 자격 증명, 보안 개체 및 권한에 대해 설명하는 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-157">Contains links to topics that describe principals, roles, credentials, securables and permissions.</span></span>|  
|[<span data-ttu-id="1fbd7-158">보안 주체</span><span class="sxs-lookup"><span data-stu-id="1fbd7-158">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="1fbd7-159">보안 주체에 대해 설명하며 서버 및 데이터베이스 역할에 대해 설명하는 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-159">Describes principals and contains links to topics that describe server and database roles.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fbd7-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fbd7-160">See also</span></span>

- [<span data-ttu-id="1fbd7-161">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="1fbd7-161">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="1fbd7-162">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="1fbd7-162">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="1fbd7-163">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="1fbd7-163">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="1fbd7-164">SQL Server에서 소유권 및 사용자와 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="1fbd7-164">Ownership and User-Schema Separation in SQL Server</span></span>](ownership-and-user-schema-separation-in-sql-server.md)
- [<span data-ttu-id="1fbd7-165">SQL Server에서 권한 부여 및 권한</span><span class="sxs-lookup"><span data-stu-id="1fbd7-165">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="1fbd7-166">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="1fbd7-166">ADO.NET Overview</span></span>](../ado-net-overview.md)
