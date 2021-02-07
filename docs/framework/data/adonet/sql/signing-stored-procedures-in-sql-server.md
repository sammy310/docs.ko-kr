---
description: '자세한 정보: SQL Server에서 저장 프로시저 서명'
title: SQL Server에서 저장 프로시저에 서명
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 1189f3ac24c8499cd8fb3ff9e6b6263a71fcc3a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767507"
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="94adc-103">SQL Server에서 저장 프로시저에 서명</span><span class="sxs-lookup"><span data-stu-id="94adc-103">Signing Stored Procedures in SQL Server</span></span>

<span data-ttu-id="94adc-104">디지털 설명은 서명자의 프라이빗 키로 암호화된 데이터 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-104">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="94adc-105">프라이빗 키를 사용하면 디지털 서명이 소유자별로 고유하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-105">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="94adc-106">저장 프로시저, 함수 (인라인 테이블 반환 함수 제외), 트리거 및 어셈블리에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-106">You can sign stored procedures, functions (except for inline table-valued functions), triggers, and assemblies.</span></span>

<span data-ttu-id="94adc-107">인증서나 비대칭 키를 사용하여 저장 프로시저에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-107">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="94adc-108">이 기능은 권한을 소유권 체인을 통해 상속할 수 없거나 동적 SQL과 같이 소유권 체인이 끊어진 시나리오를 위해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-108">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="94adc-109">그런 다음 인증서에 매핑된 사용자를 만들어 저장 프로시저에서 액세스 해야 하는 개체에 대 한 인증서 사용자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-109">You can then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>

<span data-ttu-id="94adc-110">동일한 인증서에 매핑된 로그인을 만든 다음이 로그인에 필요한 서버 수준 사용 권한을 부여 하거나 하나 이상의 고정 서버 역할에 로그인을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-110">You can also create a login mapped to the same certificate, and then grant any necessary server-level permissions to that login, or add the login to one or more of the fixed server roles.</span></span> <span data-ttu-id="94adc-111">이는 `TRUSTWORTHY` 더 높은 수준의 권한이 필요한 시나리오에 대 한 데이터베이스 설정을 사용 하지 않도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-111">This is designed to avoid enabling the `TRUSTWORTHY` database setting for scenarios in which higher level permissions are needed.</span></span>

<span data-ttu-id="94adc-112">저장 프로시저를 실행 하면 SQL Server는 인증서 사용자 및/또는 로그인의 사용 권한을 호출자의 권한과 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-112">When the stored procedure is executed, SQL Server combines the permissions of the certificate user and/or login with those of the caller.</span></span> <span data-ttu-id="94adc-113">절과 달리 `EXECUTE AS` 프로시저의 실행 컨텍스트는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-113">Unlike the `EXECUTE AS` clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="94adc-114">로그인과 사용자 이름을 반환하는 기본 제공 함수는 인증서 사용자 이름이 아니라 호출자의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-114">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>

## <a name="creating-certificates"></a><span data-ttu-id="94adc-115">인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="94adc-115">Creating Certificates</span></span>

<span data-ttu-id="94adc-116">인증서 나 비대칭 키를 사용 하 여 저장 프로시저에 서명 하는 경우 실행 사용자와 함께 저장 프로시저 코드의 암호화 된 해시로 구성 된 데이터 다이제스트가 개인 키를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-116">When you sign a stored procedure with a certificate or asymmetric key, a data digest consisting of the encrypted hash of the stored procedure code, along with the execute-as user, is created using the private key.</span></span> <span data-ttu-id="94adc-117">런타임에 데이터 다이제스트는 공개 키로 암호 해독되어 저장 프로시저의 해시 값과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-117">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="94adc-118">Execute as user를 변경 하면 디지털 서명이 더 이상 일치 하지 않도록 해시 값이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-118">Changing the execute-as user invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="94adc-119">저장 프로시저를 수정 하면 서명이 완전히 삭제 되므로 개인 키에 대 한 액세스 권한이 없는 사용자가 저장 프로시저 코드를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-119">Modifying the stored procedure drops the signature entirely, which prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="94adc-120">두 경우 모두 코드 또는 실행 사용자를 변경할 때마다 프로시저에 다시 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-120">In either case, you must re-sign the procedure each time you change the code or the execute-as user.</span></span>

<span data-ttu-id="94adc-121">모듈에 서명 하는 데는 다음과 같은 두 가지 필수 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-121">There are two required steps involved in signing a module:</span></span>

1. <span data-ttu-id="94adc-122">Transact-SQL `CREATE CERTIFICATE [certificateName]` 문을 사용하여 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-122">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="94adc-123">이 문에는 시작 및 종료 날짜와 암호를 설정하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-123">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="94adc-124">기본 만료 날짜는 1 년입니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-124">The default expiration date is one year.</span></span>

1. <span data-ttu-id="94adc-125">Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 문을 사용하여 프로시저에 인증서로 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-125">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>

<span data-ttu-id="94adc-126">모듈이 서명 되 면 인증서와 연결 되어야 하는 추가 권한을 보유 하기 위해 하나 이상의 보안 주체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-126">Once the module has been signed, one or more principals needs to be created in order to hold the additional permissions that should be associated with the certificate.</span></span>

<span data-ttu-id="94adc-127">모듈에 추가 데이터베이스 수준 사용 권한이 필요한 경우:</span><span class="sxs-lookup"><span data-stu-id="94adc-127">If the module needs additional database-level permissions:</span></span>

1. <span data-ttu-id="94adc-128">Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 문을 사용하여 해당 인증서와 연결된 데이터베이스 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-128">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="94adc-129">이 사용자는 데이터베이스에만 존재 하며 동일한 인증서에서 로그인을 만들지 않은 경우 로그인과 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-129">This user exists in the database only and is not associated with a login unless a login has also been created from that same certificate.</span></span>

1. <span data-ttu-id="94adc-130">필요한 데이터베이스 수준 사용 권한을 인증서 사용자에 게 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-130">Grant the certificate user the required database-level permissions.</span></span>

<span data-ttu-id="94adc-131">모듈에 추가 서버 수준 사용 권한이 필요한 경우:</span><span class="sxs-lookup"><span data-stu-id="94adc-131">If the module needs additional server-level permissions:</span></span>

1. <span data-ttu-id="94adc-132">인증서를 데이터베이스에 복사 `master` 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-132">Copy the certificate to the `master` database.</span></span>

1. <span data-ttu-id="94adc-133">Transact-sql 문을 사용 하 여 해당 인증서와 연결 된 로그인을 만듭니다 `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` .</span><span class="sxs-lookup"><span data-stu-id="94adc-133">Create a login associated with that certificate using the Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` statement.</span></span>

1. <span data-ttu-id="94adc-134">인증서 로그인에 필요한 서버 수준 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-134">Grant the certificate login the required server-level permissions.</span></span>

> [!NOTE]
> <span data-ttu-id="94adc-135">인증서는 DENY 문을 사용하여 호출된 권한을 가진 사용자에게 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-135">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="94adc-136">DENY는 항상 GRANT보다 높은 우선 순위를 갖기 때문에 호출자가 인증서 사용자에게 부여된 권한을 상속 받지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-136">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>

## <a name="external-resources"></a><span data-ttu-id="94adc-137">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="94adc-137">External Resources</span></span>

<span data-ttu-id="94adc-138">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94adc-138">For more information, see the following resources.</span></span>

|<span data-ttu-id="94adc-139">리소스</span><span class="sxs-lookup"><span data-stu-id="94adc-139">Resource</span></span>|<span data-ttu-id="94adc-140">설명</span><span class="sxs-lookup"><span data-stu-id="94adc-140">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="94adc-141">[모듈 서명](/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="94adc-141">[Module Signing](/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))</span></span>|<span data-ttu-id="94adc-142">모듈 서명에 대해 설명 하 고 샘플 시나리오와 관련 Transact-sql 문서에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-142">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL articles.</span></span>|
|[<span data-ttu-id="94adc-143">인증서로 저장 프로시저 서명</span><span class="sxs-lookup"><span data-stu-id="94adc-143">Signing Stored Procedures with a Certificate</span></span>](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|<span data-ttu-id="94adc-144">인증서로 저장 프로시저에 서명하는 방법에 대한 자습서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94adc-144">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|

## <a name="see-also"></a><span data-ttu-id="94adc-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94adc-145">See also</span></span>

- [<span data-ttu-id="94adc-146">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="94adc-146">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="94adc-147">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="94adc-147">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="94adc-148">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="94adc-148">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="94adc-149">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="94adc-149">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="94adc-150">SQL Server에서 보안 동적 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="94adc-150">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="94adc-151">SQL Server에서 가장으로 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="94adc-151">Customizing Permissions with Impersonation in SQL Server</span></span>](customizing-permissions-with-impersonation-in-sql-server.md)
- [<span data-ttu-id="94adc-152">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="94adc-152">Modifying Data with Stored Procedures</span></span>](../modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="94adc-153">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="94adc-153">ADO.NET Overview</span></span>](../ado-net-overview.md)
