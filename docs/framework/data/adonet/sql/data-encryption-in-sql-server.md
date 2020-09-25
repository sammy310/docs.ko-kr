---
title: SQL Server에서 데이터 암호화
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: d0bda11f1a2933d096aa91d2be79d3af35172284
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169533"
---
# <a name="data-encryption-in-sql-server"></a><span data-ttu-id="79fb1-102">SQL Server에서 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="79fb1-102">Data Encryption in SQL Server</span></span>

<span data-ttu-id="79fb1-103">SQL Server에는 인증서, 비대칭 키 또는 대칭 키를 사용하여 데이터를 암호화하고 해독하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-103">SQL Server provides functions to encrypt and decrypt data using a certificate, asymmetric key, or symmetric key.</span></span> <span data-ttu-id="79fb1-104">또한 SQL Server 2005는 내부 인증서 저장소에서 이러한 모든 항목을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-104">It manages all of these in an internal certificate store.</span></span> <span data-ttu-id="79fb1-105">이 저장소는 계층 구조에서 한 단계 상위에 있는 계층에서 인증서와 키를 보호하는 암호화 계층 구조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-105">The store uses an encryption hierarchy that secures certificates and keys at one level with the layer above it in the hierarchy.</span></span> <span data-ttu-id="79fb1-106">SQL Server의 이 기능 영역을 비밀 스토리지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-106">This feature area of SQL Server is called Secret Storage.</span></span>  
  
 <span data-ttu-id="79fb1-107">암호화 기능에서 지원하는 가장 빠른 암호화 모드는 대칭 키 암호화입니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-107">The fastest mode of encryption supported by the encryption functions is symmetric key encryption.</span></span> <span data-ttu-id="79fb1-108">이 모드는 대량 데이터 처리에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-108">This mode is suitable for handling large volumes of data.</span></span> <span data-ttu-id="79fb1-109">대칭 키는 인증서, 암호 또는 다른 대칭 키를 사용하여 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-109">The symmetric keys can be encrypted by certificates, passwords or other symmetric keys.</span></span>  
  
## <a name="keys-and-algorithms"></a><span data-ttu-id="79fb1-110">키 및 알고리즘</span><span class="sxs-lookup"><span data-stu-id="79fb1-110">Keys and Algorithms</span></span>  

 <span data-ttu-id="79fb1-111">SQL Server는 DES, Triple DES, RC2, RC4, 128비트 RC4, DESX, 128비트 AES, 192비트 AES 및 256비트 AES를 비롯한 다양한 대칭 키 암호화 알고리즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-111">SQL Server supports several symmetric key encryption algorithms, including DES, Triple DES, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span> <span data-ttu-id="79fb1-112">이러한 알고리즘은 Windows Crypto API를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-112">The algorithms are implemented using the Windows Crypto API.</span></span>  
  
 <span data-ttu-id="79fb1-113">데이터베이스 연결 범위 내에서 SQL Server는 공개 대칭 키를 여러 개 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-113">Within the scope of a database connection, SQL Server can maintain multiple open symmetric keys.</span></span> <span data-ttu-id="79fb1-114">저장소에서 공개 키를 검색하여 데이터 암호 해독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-114">An open key is retrieved from the store and is available for decrypting data.</span></span> <span data-ttu-id="79fb1-115">데이터 암호를 해독할 때에는 사용할 대칭 키를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-115">When a piece of data is decrypted, there is no need to specify the symmetric key to use.</span></span> <span data-ttu-id="79fb1-116">각각의 암호화된 값에는 해독에 사용되는 키의 키 식별자(키 GUID)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-116">Each encrypted value contains the key identifier (key GUID) of the key used to encrypt it.</span></span> <span data-ttu-id="79fb1-117">엔진은 암호화된 바이트 스트림과 일치하는 공개 대칭 키를 찾아 올바른 키를 암호 해독하고 열었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-117">The engine matches the encrypted byte stream to an open symmetric key, if the correct key has been decrypted and is open.</span></span> <span data-ttu-id="79fb1-118">그런 다음 이 키를 사용하여 암호 해독을 수행하고 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-118">This key is then used to perform decryption and return the data.</span></span> <span data-ttu-id="79fb1-119">올바른 키가 열려 있지 않으면 NULL이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-119">If the correct key is not open, NULL is returned.</span></span>  
  
 <span data-ttu-id="79fb1-120">데이터베이스에서 암호화 된 데이터를 사용 하는 방법을 보여 주는 예는 [데이터 열 암호화](/sql/relational-databases/security/encryption/encrypt-a-column-of-data)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79fb1-120">For an example that shows how to work with encrypted data in a database, see [Encrypt a Column of Data](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).</span></span>
  
## <a name="external-resources"></a><span data-ttu-id="79fb1-121">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="79fb1-121">External Resources</span></span>  

 <span data-ttu-id="79fb1-122">데이터 암호화에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79fb1-122">For more information on data encryption, see the following resources.</span></span>  
  
|<span data-ttu-id="79fb1-123">리소스</span><span class="sxs-lookup"><span data-stu-id="79fb1-123">Resource</span></span>|<span data-ttu-id="79fb1-124">설명</span><span class="sxs-lookup"><span data-stu-id="79fb1-124">Description</span></span>|  
|-|-|  
|[<span data-ttu-id="79fb1-125">SQL Server 암호화</span><span class="sxs-lookup"><span data-stu-id="79fb1-125">SQL Server Encryption</span></span>](/sql/relational-databases/security/encryption/sql-server-encryption)|<span data-ttu-id="79fb1-126">SQL Server의 암호화에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-126">Provides an overview of encryption in SQL Server.</span></span> <span data-ttu-id="79fb1-127">이 항목에는 추가 문서에 대 한 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-127">This topic includes links to additional articles.</span></span>|  
|[<span data-ttu-id="79fb1-128">암호화 계층</span><span class="sxs-lookup"><span data-stu-id="79fb1-128">Encryption Hierarchy</span></span>](/sql/relational-databases/security/encryption/encryption-hierarchy)|<span data-ttu-id="79fb1-129">SQL Server의 암호화에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-129">Provides an overview of encryption in SQL Server.</span></span> <span data-ttu-id="79fb1-130">이 항목에서는 추가 문서에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79fb1-130">This topic provides links to additional articles.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79fb1-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79fb1-131">See also</span></span>

- [<span data-ttu-id="79fb1-132">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="79fb1-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="79fb1-133">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="79fb1-133">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="79fb1-134">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="79fb1-134">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="79fb1-135">SQL Server의 서버 및 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="79fb1-135">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)
- [<span data-ttu-id="79fb1-136">SQL Server에서 소유권 및 사용자와 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="79fb1-136">Ownership and User-Schema Separation in SQL Server</span></span>](ownership-and-user-schema-separation-in-sql-server.md)
- [<span data-ttu-id="79fb1-137">SQL Server에서 권한 부여 및 권한</span><span class="sxs-lookup"><span data-stu-id="79fb1-137">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="79fb1-138">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="79fb1-138">ADO.NET Overview</span></span>](../ado-net-overview.md)
