---
title: SQL Server에서 가장으로 권한 사용자 지정
ms.date: 03/30/2017
ms.assetid: dc733d09-1d6d-4af0-9c4b-8d24504860f1
ms.openlocfilehash: 84c5585912ba259fdcefaae186138c4466b16206
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180857"
---
# <a name="customizing-permissions-with-impersonation-in-sql-server"></a><span data-ttu-id="b84a3-102">SQL Server에서 가장으로 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b84a3-102">Customizing Permissions with Impersonation in SQL Server</span></span>

<span data-ttu-id="b84a3-103">많은 수의 애플리케이션에서 저장 프로시저를 사용하여 데이터에 액세스하며, 이 경우 소유권 체인을 사용하여 액세스를 기본 테이블로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-103">Many applications use stored procedures to access data, relying on ownership chaining to restrict access to base tables.</span></span> <span data-ttu-id="b84a3-104">저장 프로시저에 EXECUTE 권한을 부여하고 기본 테이블에 대한 권한을 취소하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-104">You can grant EXECUTE permissions on stored procedures, revoking or denying permissions on the base tables.</span></span> <span data-ttu-id="b84a3-105">SQL Server에서는 저장 프로시저 및 테이블의 소유자가 동일한 경우 호출자의 권한을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-105">SQL Server does not check the permissions of the caller if the stored procedure and tables have the same owner.</span></span> <span data-ttu-id="b84a3-106">그러나 개체의 소유자가 다른 경우 또는 동적 SQL의 경우에는 소유권 체인이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-106">However, ownership chaining doesn't work if objects have different owners or in the case of dynamic SQL.</span></span>  
  
 <span data-ttu-id="b84a3-107">참조되는 데이터베이스 개체에 대한 권한이 호출자에게 없을 때 저장 프로시저에 EXECUTE AS 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-107">You can use the EXECUTE AS clause in a stored procedure when the caller doesn't have permissions on the referenced database objects.</span></span> <span data-ttu-id="b84a3-108">EXECUTE AS 절의 효과는 실행 컨텍스트가 프록시 사용자로 전환된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-108">The effect of the EXECUTE AS clause is that the execution context is switched to the proxy user.</span></span> <span data-ttu-id="b84a3-109">중첩된 저장 프로시저나 트리거에 대한 모든 호출 및 모든 코드는 프록시 사용자의 보안 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-109">All code, as well as any calls to nested stored procedures or triggers, executes under the security context of the proxy user.</span></span> <span data-ttu-id="b84a3-110">실행 컨텍스트는 프로시저 실행 후 또는 REVERT 문이 실행된 후에만 원래 호출자로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-110">Execution context is reverted to the original caller only after execution of the procedure or when a REVERT statement is issued.</span></span>  
  
## <a name="context-switching-with-the-execute-as-statement"></a><span data-ttu-id="b84a3-111">EXECUTE AS 문을 사용하여 컨텍스트 전환</span><span class="sxs-lookup"><span data-stu-id="b84a3-111">Context Switching with the EXECUTE AS Statement</span></span>  

 <span data-ttu-id="b84a3-112">Transact-SQL의 EXECUTE AS 문을 사용하면 다른 로그인 또는 데이터베이스 사용자를 가장하여 문의 실행 컨텍스트를 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-112">The Transact-SQL EXECUTE AS statement allows you to switch the execution context of a statement by impersonating another login or database user.</span></span> <span data-ttu-id="b84a3-113">이 방법은 쿼리와 프로시저를 다른 사용자로 테스트할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-113">This is a useful technique for testing queries and procedures as another user.</span></span>  
  
```sql  
EXECUTE AS LOGIN = 'loginName';  
EXECUTE AS USER = 'userName';  
```  
  
 <span data-ttu-id="b84a3-114">현재 가장하고 있는 로그인 또는 사용자에 대해 IMPERSONATE 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-114">You must have IMPERSONATE permissions on the login or user you are impersonating.</span></span> <span data-ttu-id="b84a3-115">이 권한은 모든 데이터베이스에 대해 `sysadmin` 권한이 있고 소유한 데이터베이스에서 `db_owner` 역할 멤버인 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-115">This permission is implied for `sysadmin` for all databases, and `db_owner` role members in databases that they own.</span></span>  
  
## <a name="granting-permissions-with-the-execute-as-clause"></a><span data-ttu-id="b84a3-116">EXECUTE AS 절을 사용하여 권한 부여</span><span class="sxs-lookup"><span data-stu-id="b84a3-116">Granting Permissions with the EXECUTE AS Clause</span></span>  

 <span data-ttu-id="b84a3-117">저장 프로시저, 트리거 또는 사용자 정의 함수(인라인 테이블 반환 함수 제외)의 정의 헤더에 EXECUTE AS 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-117">You can use the EXECUTE AS clause in the definition header of a stored procedure, trigger, or user-defined function (except for inline table-valued functions).</span></span> <span data-ttu-id="b84a3-118">이렇게 하면 사용자 이름 또는 EXECUTE AS 절에 지정된 키워드의 컨텍스트에서 프로시저를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-118">This causes the procedure to execute in the context of the user name or keyword specified in the EXECUTE AS clause.</span></span> <span data-ttu-id="b84a3-119">로그인에 매핑되지 않은 데이터베이스에 프록시 사용자를 만들고 프로시저가 액세스하는 개체에 대해 필요한 권한만 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-119">You can create a proxy user in the database that is not mapped to a login, granting it only the necessary permissions on the objects accessed by the procedure.</span></span> <span data-ttu-id="b84a3-120">EXECUTE AS 절에 지정된 프록시 사용자에게만 모듈에서 액세스하는 모든 개체에 대한 권한이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-120">Only the proxy user specified in the EXECUTE AS clause must have permissions on all objects accessed by the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b84a3-121">TRUNCATE TABLE과 같은 일부 작업에는 부여할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-121">Some actions, such as TRUNCATE TABLE, do not have grantable permissions.</span></span> <span data-ttu-id="b84a3-122">문을 프로시저 내에 포함하고 ALTER TABLE 권한이 있는 사용자를 지정하면 테이블을 자르는 권한을 프로시저에 대해 EXECUTE 권한만 가진 호출자로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-122">By incorporating the statement within a procedure and specifying a proxy user who has ALTER TABLE permissions, you can extend the permissions to truncate the table to callers who have only EXECUTE permissions on the procedure.</span></span>  
  
 <span data-ttu-id="b84a3-123">EXECUTE AS 절에 지정된 컨텍스트는 중첩된 프로시저 및 트리거를 포함하여 프로시저의 실행 기간 동안 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-123">The context specified in the EXECUTE AS clause is valid for the duration of the procedure, including nested procedures and triggers.</span></span> <span data-ttu-id="b84a3-124">실행이 완료되거나 REVERT 문이 실행되면 컨텍스트가 호출자에게 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-124">Context reverts to the caller when execution is complete or the REVERT statement is issued.</span></span>  
  
 <span data-ttu-id="b84a3-125">프로시저에서 EXECUTE AS 절을 사용할 때는 다음 세 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-125">There are three steps involved in using the EXECUTE AS clause in a procedure.</span></span>  
  
1. <span data-ttu-id="b84a3-126">로그인에 매핑되지 않는 데이터베이스에 프록시 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-126">Create a proxy user in the database that is not mapped to a login.</span></span> <span data-ttu-id="b84a3-127">이 단계는 필수 사항은 아니지만 권한 관리에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-127">This is not required, but it helps when managing permissions.</span></span>  
  
```sql
CREATE USER proxyUser WITHOUT LOGIN  
```  
  
1. <span data-ttu-id="b84a3-128">프록시 사용자에게 필요한 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-128">Grant the proxy user the necessary permissions.</span></span>  
  
2. <span data-ttu-id="b84a3-129">저장 프로시저 또는 사용자 정의 함수에 EXECUTE AS 절을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-129">Add the EXECUTE AS clause to the stored procedure or user-defined function.</span></span>  
  
```sql
CREATE PROCEDURE [procName] WITH EXECUTE AS 'proxyUser' AS ...  
```  
  
> [!NOTE]
> <span data-ttu-id="b84a3-130">호출자의 원래 보안 컨텍스트가 유지되지 않기 때문에 감사가 필요한 애플리케이션은 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-130">Applications that require auditing can break because the original security context of the caller is not retained.</span></span> <span data-ttu-id="b84a3-131">SESSION_USER, USER 또는 USER_NAME과 같이 현재 사용자의 ID를 반환하는 기본 제공 함수는 원래 호출자가 아니라 EXECUTE AS 절과 연관된 사용자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-131">Built-in functions that return the identity of the current user, such as SESSION_USER, USER, or USER_NAME, return the user associated with the EXECUTE AS clause, not the original caller.</span></span>  
  
### <a name="using-execute-as-with-revert"></a><span data-ttu-id="b84a3-132">REVERT와 함께 EXECUTE AS 사용</span><span class="sxs-lookup"><span data-stu-id="b84a3-132">Using EXECUTE AS with REVERT</span></span>  

 <span data-ttu-id="b84a3-133">Transact-SQL REVERT 문을 사용하여 원래 실행 컨텍스트로 되돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-133">You can use the Transact-SQL REVERT statement to revert to the original execution context.</span></span>  
  
 <span data-ttu-id="b84a3-134">선택적 절 (NO REVERT COOKIE =)을 사용 하면 @variableName 변수에 올바른 값이 포함 된 경우 실행 컨텍스트를 다시 호출자로 전환할 수 있습니다 @variableName .</span><span class="sxs-lookup"><span data-stu-id="b84a3-134">The optional clause, WITH NO REVERT COOKIE = @variableName, allows you switch the execution context back to the caller if the @variableName variable contains the correct value.</span></span> <span data-ttu-id="b84a3-135">이를 통해 연결 풀링이 사용되는 환경에서 실행 컨텍스트를 다시 호출자로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-135">This allows you to switch the execution context back to the caller in environments where connection pooling is used.</span></span> <span data-ttu-id="b84a3-136">의 값은 @variableName EXECUTE AS 문의 호출자 에게만 알려져 있으므로 호출자는 응용 프로그램을 호출 하는 최종 사용자가 실행 컨텍스트를 변경할 수 없도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-136">Because the value of @variableName is known only to the caller of the EXECUTE AS statement, the caller can guarantee that the execution context cannot be changed by the end user that invokes the application.</span></span> <span data-ttu-id="b84a3-137">연결이 닫히면 연결은 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-137">When the connection is closed, it is returned to the pool.</span></span> <span data-ttu-id="b84a3-138">ADO.NET의 연결 풀링에 대 한 자세한 내용은 [연결 풀링 (ADO.NET) SQL Server](../sql-server-connection-pooling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b84a3-138">For more information on connection pooling in ADO.NET, see [SQL Server Connection Pooling (ADO.NET)](../sql-server-connection-pooling.md).</span></span>  
  
### <a name="specifying-the-execution-context"></a><span data-ttu-id="b84a3-139">실행 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="b84a3-139">Specifying the Execution Context</span></span>  

 <span data-ttu-id="b84a3-140">사용자 지정 외에도 EXECUTE AS는 다음 키워드와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-140">In addition to specifying a user, you can also use EXECUTE AS with any of the following keywords.</span></span>  
  
- <span data-ttu-id="b84a3-141">CALLER.</span><span class="sxs-lookup"><span data-stu-id="b84a3-141">CALLER.</span></span> <span data-ttu-id="b84a3-142">기본적으로 CALLER로 실행됩니다. 다른 옵션을 지정하지 않으면 프로시저는 호출자의 보안 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-142">Executing as CALLER is the default; if no other option is specified, then the procedure executes in the security context of the caller.</span></span>  
  
- <span data-ttu-id="b84a3-143">OWNER.</span><span class="sxs-lookup"><span data-stu-id="b84a3-143">OWNER.</span></span> <span data-ttu-id="b84a3-144">OWNER로 실행할 경우 프로시저는 프로시저 소유자의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-144">Executing as OWNER executes the procedure in the context of the procedure owner.</span></span> <span data-ttu-id="b84a3-145">`dbo` 또는 데이터베이스 소유자가 소유한 스키마에서 만들어진 프로시저는 무제한 권한으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-145">If the procedure is created in a schema owned by `dbo` or the database owner, the procedure will execute with unrestricted permissions.</span></span>  
  
- <span data-ttu-id="b84a3-146">SELF.</span><span class="sxs-lookup"><span data-stu-id="b84a3-146">SELF.</span></span> <span data-ttu-id="b84a3-147">SELF로 실행할 경우 저장 프로시저 작성자의 보안 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-147">Executing as SELF executes in the security context of the creator of the stored procedure.</span></span> <span data-ttu-id="b84a3-148">지정된 사용자로 실행하는 것과 같으며, 여기서 지정된 사용자는 프로시저를 만들거나 변경하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b84a3-148">This is equivalent to executing as a specified user, where the specified user is the person creating or altering the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84a3-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b84a3-149">See also</span></span>

- [<span data-ttu-id="b84a3-150">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="b84a3-150">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="b84a3-151">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="b84a3-151">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="b84a3-152">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="b84a3-152">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="b84a3-153">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="b84a3-153">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="b84a3-154">SQL Server에서 보안 동적 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="b84a3-154">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="b84a3-155">SQL Server에서 저장 프로시저에 서명</span><span class="sxs-lookup"><span data-stu-id="b84a3-155">Signing Stored Procedures in SQL Server</span></span>](signing-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="b84a3-156">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="b84a3-156">Modifying Data with Stored Procedures</span></span>](../modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="b84a3-157">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b84a3-157">ADO.NET Overview</span></span>](../ado-net-overview.md)
