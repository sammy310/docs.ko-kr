---
title: SQL Server에서 애플리케이션 역할 만들기
ms.date: 03/30/2017
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
ms.openlocfilehash: 764ae61cba4bf01681d658cc4aacc2aeaecedd3f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173551"
---
# <a name="creating-application-roles-in-sql-server"></a><span data-ttu-id="9c112-102">SQL Server에서 애플리케이션 역할 만들기</span><span class="sxs-lookup"><span data-stu-id="9c112-102">Creating Application Roles in SQL Server</span></span>

<span data-ttu-id="9c112-103">애플리케이션 역할을 사용하면 데이터베이스 역할이나 사용자 대신 애플리케이션에 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-103">Application roles provide a way to assign permissions to an application instead of a database role or user.</span></span> <span data-ttu-id="9c112-104">사용자는 데이터베이스에 연결한 후 애플리케이션 역할을 활성화하여 애플리케이션에 부여된 권한을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-104">Users can connect to the database, activate the application role, and assume the permissions granted to the application.</span></span> <span data-ttu-id="9c112-105">애플리케이션 역할에 부여된 권한은 연결되어 있는 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-105">The permissions granted to the application role are in force for the duration of the connection.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9c112-106">애플리케이션 역할은 클라이언트 애플리케이션에서 연결 문자열에 애플리케이션 역할 이름과 암호를 제공하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-106">Application roles are activated when a client application supplies an application role name and a password in the connection string.</span></span> <span data-ttu-id="9c112-107">암호는 클라이언트 컴퓨터에 저장되므로 2계층 애플리케이션의 경우 애플리케이션 역할로 인해 보안상 취약한 부분이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-107">They present a security vulnerability in a two-tier application because the password must be stored on the client computer.</span></span> <span data-ttu-id="9c112-108">3계층 애플리케이션에서는 애플리케이션 사용자가 액세스할 수 없는 방식으로 암호를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-108">In a three-tier application, you can store the password so that it cannot be accessed by users of the application.</span></span>  
  
## <a name="application-role-features"></a><span data-ttu-id="9c112-109">애플리케이션 역할의 특징</span><span class="sxs-lookup"><span data-stu-id="9c112-109">Application Role Features</span></span>  

 <span data-ttu-id="9c112-110">애플리케이션 역할에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-110">Application roles have the following features:</span></span>  
  
- <span data-ttu-id="9c112-111">데이터베이스 역할과 달리 애플리케이션 역할은 멤버를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-111">Unlike database roles, application roles contain no members.</span></span>  
  
- <span data-ttu-id="9c112-112">애플리케이션 역할은 애플리케이션에서 `sp_setapprole` 시스템 저장 프로시저에 애플리케이션 역할 이름과 암호를 제공하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-112">Application roles are activated when an application supplies the application role name and a password to the `sp_setapprole` system stored procedure.</span></span>  
  
- <span data-ttu-id="9c112-113">암호는 클라이언트 컴퓨터에 저장되어 런타임에 제공되어야 하므로 SQL Server 내에서는 애플리케이션 역할을 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-113">The password must be stored on the client computer and supplied at run time; an application role cannot be activated from inside of SQL Server.</span></span>  
  
- <span data-ttu-id="9c112-114">암호가 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-114">The password is not encrypted.</span></span> <span data-ttu-id="9c112-115">매개 변수 암호는 단방향 해시로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-115">The parameter password is stored as a one-way hash.</span></span>  
  
- <span data-ttu-id="9c112-116">애플리케이션 역할이 활성화된 후 애플리케이션 역할을 통해 얻은 권한은 연결 기간 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-116">Once activated, permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
- <span data-ttu-id="9c112-117">애플리케이션 역할은 `public` 역할에 부여된 권한을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-117">The application role inherits permissions granted to the `public` role.</span></span>  
  
- <span data-ttu-id="9c112-118">`sysadmin` 고정 서버 역할의 멤버가 애플리케이션 역할을 활성화하는 경우, 연결 기간 동안 보안 컨텍스트가 해당 애플리케이션 역할의 보안 컨텍스트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-118">If a member of the `sysadmin` fixed server role activates an application role, the security context switches to that of the application role for the duration of the connection.</span></span>  
  
- <span data-ttu-id="9c112-119">애플리케이션 역할이 있는 데이터베이스에 `guest` 계정을 만들면 해당 애플리케이션 역할 또는 역할을 호출하는 어떤 로그인에 대해서도 데이터베이스 사용자 계정을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-119">If you create a `guest` account in a database that has an application role, you do not need to create a database user account for the application role or for any of the logins that invoke it.</span></span> <span data-ttu-id="9c112-120">애플리케이션 역할은 다른 데이터베이스에 `guest` 계정이 있는 경우에만 해당 데이터베이스에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-120">Application roles can directly access another database only if a `guest` account exists in the second database</span></span>  
  
- <span data-ttu-id="9c112-121">SYSTEM_USER와 같은 로그인 이름을 반환하는 기본 제공 함수가 애플리케이션 역할을 호출한 로그인의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-121">Built-in functions that return login names, such as SYSTEM_USER, return the name of the login that invoked the application role.</span></span> <span data-ttu-id="9c112-122">데이터베이스 사용자 이름을 반환하는 기본 제공 함수는 애플리케이션 역할의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-122">Built-in functions that return database user names return the name of the application role.</span></span>  
  
### <a name="the-principle-of-least-privilege"></a><span data-ttu-id="9c112-123">최소 권한의 원칙</span><span class="sxs-lookup"><span data-stu-id="9c112-123">The Principle of Least Privilege</span></span>  

 <span data-ttu-id="9c112-124">암호가 손상될 경우에 대비하여 애플리케이션 역할에는 반드시 필요한 권한만 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-124">Application roles should be granted only required permissions in case the password is compromised.</span></span> <span data-ttu-id="9c112-125">`public` 역할에 부여된 권한은 애플리케이션 역할을 사용하는 모든 데이터베이스에서 해지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-125">Permissions to the `public` role should be revoked in any database using an application role.</span></span> <span data-ttu-id="9c112-126">애플리케이션 역할 호출자가 액세스할 수 없도록 하려는 모든 데이터베이스에서 `guest` 계정을 비활성화하세요.</span><span class="sxs-lookup"><span data-stu-id="9c112-126">Disable the `guest` account in any database you do not want callers of the application role to have access to.</span></span>  
  
### <a name="application-role-enhancements"></a><span data-ttu-id="9c112-127">애플리케이션 역할의 향상된 기능</span><span class="sxs-lookup"><span data-stu-id="9c112-127">Application Role Enhancements</span></span>  

 <span data-ttu-id="9c112-128">애플리케이션 역할을 활성화한 후 실행 컨텍스트를 원래 호출자로 되돌릴 수 있으므로 연결 풀링을 비활성화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-128">The execution context can be switched back to the original caller after activating an application role, removing the need to disable connection pooling.</span></span> <span data-ttu-id="9c112-129">호출자 관련 컨텍스트 정보가 포함된 쿠키를 만드는 새로운 옵션이 `sp_setapprole` 프로시저에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-129">The `sp_setapprole` procedure has a new option that creates a cookie, which contains context information about the caller.</span></span> <span data-ttu-id="9c112-130">`sp_unsetapprole` 프로시저를 호출하고 이 프로시저에 쿠키를 전달하면 세션을 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-130">You can revert the session by calling the `sp_unsetapprole` procedure, passing it the cookie.</span></span>  
  
## <a name="application-role-alternatives"></a><span data-ttu-id="9c112-131">애플리케이션 역할의 대안</span><span class="sxs-lookup"><span data-stu-id="9c112-131">Application Role Alternatives</span></span>  

 <span data-ttu-id="9c112-132">애플리케이션 역할은 암호로 보호되는데 이로 인해 보안상 취약한 부분이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-132">Application roles depend on the security of a password, which presents a potential security vulnerability.</span></span> <span data-ttu-id="9c112-133">암호가 애플리케이션 코드에 포함되거나 디스크에 저장되어 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-133">Passwords may be exposed by being embedded in application code or saved on disk.</span></span>  
  
 <span data-ttu-id="9c112-134">다음과 같은 대안을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9c112-134">You may want to consider the following alternatives.</span></span>  
  
- <span data-ttu-id="9c112-135">NO REVERT 및 WITH COOKIE 절과 함께 EXECUTE AS 문을 사용하여 컨텍스트를 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-135">Use context switching with the EXECUTE AS statement with its NO REVERT and WITH COOKIE clauses.</span></span> <span data-ttu-id="9c112-136">로그인에 매핑되지 않는 사용자 계정을 데이터베이스에 만든 다음</span><span class="sxs-lookup"><span data-stu-id="9c112-136">You can create a user account in a database that is not mapped to a login.</span></span> <span data-ttu-id="9c112-137">이 계정에 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-137">You then assign permissions to this account.</span></span> <span data-ttu-id="9c112-138">이렇게 로그인에 매핑되지 않은 사용자로 EXECUTE AS를 사용하면 암호가 아니라 권한을 기반으로 하므로 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-138">Using EXECUTE AS with a login-less user is more secure because it is permission-based, not password-based.</span></span> <span data-ttu-id="9c112-139">자세한 내용은 [SQL Server에서 가장으로 권한 사용자 지정](customizing-permissions-with-impersonation-in-sql-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c112-139">For more information, see [Customizing Permissions with Impersonation in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md).</span></span>  
  
- <span data-ttu-id="9c112-140">저장 프로시저를 인증서로 서명하여 프로시저 실행에 꼭 필요한 권한만 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-140">Sign stored procedures with certificates, granting only permission to execute the procedures.</span></span> <span data-ttu-id="9c112-141">자세한 내용은 [SQL Server에서 저장 프로시저에 서명](signing-stored-procedures-in-sql-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c112-141">For more information, see [Signing Stored Procedures in SQL Server](signing-stored-procedures-in-sql-server.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9c112-142">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="9c112-142">External Resources</span></span>  

 <span data-ttu-id="9c112-143">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c112-143">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="9c112-144">리소스</span><span class="sxs-lookup"><span data-stu-id="9c112-144">Resource</span></span>|<span data-ttu-id="9c112-145">설명</span><span class="sxs-lookup"><span data-stu-id="9c112-145">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="9c112-146">애플리케이션 역할</span><span class="sxs-lookup"><span data-stu-id="9c112-146">Application Roles</span></span>](/sql/relational-databases/security/authentication-access/application-roles)|<span data-ttu-id="9c112-147">SQL Server 2008에서 애플리케이션 역할을 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c112-147">Describes how to create and use application roles in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c112-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c112-148">See also</span></span>

- [<span data-ttu-id="9c112-149">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="9c112-149">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="9c112-150">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="9c112-150">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="9c112-151">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="9c112-151">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="9c112-152">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="9c112-152">ADO.NET Overview</span></span>](../ado-net-overview.md)
