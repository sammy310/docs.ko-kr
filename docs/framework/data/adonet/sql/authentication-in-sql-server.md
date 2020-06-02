---
title: SQL Server에서 인증
description: Windows 인증 모드 및 혼합 모드를 포함 하 여 ADO.NET에 대 한 SQL Server 인증에 대해 알아봅니다.
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: e9915598acfbdefb59069d6a9c6ef4b7c824e4c6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286548"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="7e717-103">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="7e717-103">Authentication in SQL Server</span></span>
<span data-ttu-id="7e717-104">SQL Server에서는 Windows 인증 모드와 혼합 모드의 두 가지 인증 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-104">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="7e717-105">Windows 인증은 기본 인증이며 흔히 통합 보안이라고 하는데, 그 이유는 이 SQL Server 보안 모델이 Windows와 긴밀하게 통합되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-105">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="7e717-106">특정 Windows 사용자 및 그룹 계정은 SQL Server에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-106">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="7e717-107">이미 인증된 Windows 사용자는 추가 자격 증명을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-107">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="7e717-108">혼합 모드에서는 Windows 인증과 SQL Server 인증을 모두 지원하며</span><span class="sxs-lookup"><span data-stu-id="7e717-108">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="7e717-109">사용자 이름 및 암호 쌍이 SQL Server 내에서 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-109">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e717-110">가능하면 Windows 인증을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-110">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="7e717-111">Windows 인증은 일련의 암호화된 메시지를 사용하여 SQL Server에서 사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-111">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="7e717-112">SQL Server 로그인을 사용하는 경우 SQL Server 로그인 이름과 암호화된 암호가 네트워크를 통해 전달되므로 Windows 인증에 비해 보안이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-112">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="7e717-113">Windows 인증을 사용하는 경우 사용자가 Windows에 이미 로그온되어 있으므로 SQL Server에 별도로 로그온할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-113">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="7e717-114">다음 `SqlConnection.ConnectionString`은 사용자가 사용자 이름이나 암호를 제공할 필요가 없는 Windows 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-114">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="7e717-115">로그인은 데이터베이스 사용자와 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-115">Logins are distinct from database users.</span></span> <span data-ttu-id="7e717-116">별도의 작업으로 로그인 또는 Windows 그룹을 데이터베이스 사용자 또는 역할에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-116">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="7e717-117">그런 다음 사용자 또는 역할에 데이터베이스 개체에 액세스할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-117">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="7e717-118">인증 시나리오</span><span class="sxs-lookup"><span data-stu-id="7e717-118">Authentication Scenarios</span></span>  
 <span data-ttu-id="7e717-119">Windows 인증은 일반적으로 다음과 같은 경우에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-119">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="7e717-120">도메인 컨트롤러가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e717-120">There is a domain controller.</span></span>  
  
- <span data-ttu-id="7e717-121">애플리케이션과 데이터베이스가 같은 컴퓨터에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e717-121">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="7e717-122">SQL Server Express 또는 LocalDB의 인스턴스를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="7e717-122">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="7e717-123">SQL Server 로그인은 다음과 같은 경우에 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-123">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="7e717-124">작업 그룹이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7e717-124">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="7e717-125">사용자가 신뢰할 수 없는 다른 도메인에서 연결하는 경우</span><span class="sxs-lookup"><span data-stu-id="7e717-125">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="7e717-126">ASP.NET와 같은 인터넷 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="7e717-126">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e717-127">Windows 인증을 지정하더라도 SQL Server 로그인이 비활성화되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-127">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="7e717-128">따라서 높은 수준의 권한이 있는 SQL Server 로그인은 ALTER LOGIN DISABLE Transact-SQL 문을 사용하여 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-128">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="7e717-129">로그인 유형</span><span class="sxs-lookup"><span data-stu-id="7e717-129">Login Types</span></span>  
 <span data-ttu-id="7e717-130">SQL Server에서는 세 가지 유형의 로그인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-130">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="7e717-131">로컬 Windows 사용자 계정 또는 신뢰할 수 있는 도메인 계정.</span><span class="sxs-lookup"><span data-stu-id="7e717-131">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="7e717-132">SQL Server는 Windows를 통해 Windows 사용자 계정을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-132">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="7e717-133">Windows group.</span><span class="sxs-lookup"><span data-stu-id="7e717-133">Windows group.</span></span> <span data-ttu-id="7e717-134">Windows 그룹에 액세스 권한을 부여하면 해당 그룹의 멤버인 모든 Windows 사용자 로그인에 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-134">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="7e717-135">SQL Server 로그인.</span><span class="sxs-lookup"><span data-stu-id="7e717-135">SQL Server login.</span></span> <span data-ttu-id="7e717-136">SQL Server에서는 사용자 이름과 암호 해시를 모두 master 데이터베이스에 저장하고, 내부 인증 방법을 사용하여 로그인 시도가 유효한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-136">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e717-137">SQL Server에서는 코드 서명에만 사용되는 인증서 또는 비대칭 키에서 만들어진 로그인을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-137">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="7e717-138">SQL Server에 연결할 때는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-138">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="7e717-139">혼합 모드 인증</span><span class="sxs-lookup"><span data-stu-id="7e717-139">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="7e717-140">불가피하게 혼합 모드 인증을 사용하는 경우 SQL Server 로그인을 만들어야 합니다. 이 로그인은 SQL Server에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-140">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="7e717-141">그런 다음 런타임에 SQL Server 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-141">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e717-142">SQL Server는 `sa`("시스템 관리자"의 약어)라는 SQL Server 로그인을 사용하여 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-142">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="7e717-143">`sa` 로그인에 강력한 암호를 할당하고 애플리케이션에서는 `sa` 로그인을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7e717-143">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="7e717-144">`sa` 로그인은 전체 서버에 대한 해지할 수 없는 관리 자격 증명을 갖는 `sysadmin` 고정 서버 역할에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-144">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="7e717-145">공격자가 시스템 관리자 권한으로 액세스할 경우 잠재적 피해는 무제한입니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-145">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="7e717-146">Windows `BUILTIN\Administrators` 그룹(로컬 관리자 그룹)의 모든 멤버는 기본적으로 `sysadmin` 역할의 멤버이지만 이 역할에서 멤버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-146">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="7e717-147">SQL Server는 SQL Server 로그인에 대 한 Windows 암호 정책 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-147">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="7e717-148">암호 복잡성 정책은 가능한 암호의 수를 늘려 문자 조합을 이용한 공격(brute force attacks)을 방지하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-148">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="7e717-149">SQL Server SQL Server 내에서 사용 되는 암호에 동일한 복잡성 및 만료 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-149">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e717-150">사용자 입력에서 연결 문자열을 연결하면 연결 문자열 삽입 공격에 취약해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-150">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="7e717-151"><xref:System.Data.SqlClient.SqlConnectionStringBuilder>를 사용하여 런타임에 구문이 올바른 연결 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-151">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="7e717-152">자세한 내용은 [연결 문자열 작성기](../connection-string-builders.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e717-152">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="7e717-153">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="7e717-153">External Resources</span></span>  
 <span data-ttu-id="7e717-154">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e717-154">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="7e717-155">리소스</span><span class="sxs-lookup"><span data-stu-id="7e717-155">Resource</span></span>|<span data-ttu-id="7e717-156">설명</span><span class="sxs-lookup"><span data-stu-id="7e717-156">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="7e717-157">Principals</span><span class="sxs-lookup"><span data-stu-id="7e717-157">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="7e717-158">SQL Server의 로그인 및 기타 보안 주체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e717-158">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e717-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e717-159">See also</span></span>

- [<span data-ttu-id="7e717-160">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="7e717-160">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="7e717-161">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="7e717-161">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="7e717-162">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="7e717-162">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="7e717-163">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="7e717-163">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="7e717-164">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="7e717-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
