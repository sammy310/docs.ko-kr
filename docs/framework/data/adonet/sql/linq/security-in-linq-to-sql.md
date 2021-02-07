---
description: 자세히 알아보기:의 보안 LINQ to SQL
title: LINQ to SQL의 보안
ms.date: 03/30/2017
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
ms.openlocfilehash: 3d53def25aed83d96e0d32dfc964d9b49458fad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662938"
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="bbafc-103">LINQ to SQL의 보안</span><span class="sxs-lookup"><span data-stu-id="bbafc-103">Security in LINQ to SQL</span></span>

<span data-ttu-id="bbafc-104">데이터베이스에 연결할 때는 항상 보안 위험이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-104">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="bbafc-105">LINQ to SQL에서는 SQL Server에서 데이터를 사용하는 여러 가지 새로운 방법을 제공하지만 추가적인 보안 메커니즘은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-105">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="bbafc-106">액세스 제어 및 인증</span><span class="sxs-lookup"><span data-stu-id="bbafc-106">Access Control and Authentication</span></span>  

 <span data-ttu-id="bbafc-107">LINQ to SQL에는 고유의 사용자 모델이나 인증 메커니즘이 없으므로</span><span class="sxs-lookup"><span data-stu-id="bbafc-107">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="bbafc-108">SQL Server 보안을 사용하여 개체 모델에 매핑되는 데이터베이스, 데이터베이스 테이블, 뷰 및 저장 프로시저에 대한 액세스를 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-108">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="bbafc-109">또한 사용자에게 필수적인 액세스 권한만 최소한으로 부여하고 사용자 인증을 위한 강력한 암호를 설정하도록 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="bbafc-109">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="bbafc-110">매핑 및 스키마 정보</span><span class="sxs-lookup"><span data-stu-id="bbafc-110">Mapping and Schema Information</span></span>  

 <span data-ttu-id="bbafc-111">개체 모델 또는 외부 매핑 파일의 SQL-CLR 형식 매핑 및 데이터베이스 스키마 정보를 사용하여 파일 시스템의 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-111">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="bbafc-112">개체 모델 또는 외부 매핑 파일에 액세스할 수 있는 모든 사용자가 스키마 정보를 사용할 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-112">Assume that schema information will be available to all who can access the object model or external mapping file.</span></span> <span data-ttu-id="bbafc-113">스키마 정보에 대 한 광범위 한 액세스를 방지 하려면 파일 보안 메커니즘을 사용 하 여 소스 파일 및 매핑 파일을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-113">To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="bbafc-114">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="bbafc-114">Connection Strings</span></span>  

 <span data-ttu-id="bbafc-115">가능하면 연결 문자열에 암호를 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-115">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="bbafc-116">개체 관계형 디자이너 또는 SQLMetal 명령줄 도구를 사용하는 경우 연결 문자열은 자체적으로 보안 위험 요소일 뿐 아니라 개체 모델 또는 외부 매핑 파일에 일반 텍스트로 추가될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-116">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="bbafc-117">따라서 파일 시스템을 통해 개체 모델 또는 외부 매핑 파일에 액세스할 수 있는 사용자는 누구든지 연결 문자열에 포함된 연결 암호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-117">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="bbafc-118">이러한 위험을 최소화 하려면 통합 보안을 사용 하 여 SQL Server와 신뢰할 수 있는 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-118">To minimize such risks, use integrated security to make a trusted connection with SQL Server.</span></span> <span data-ttu-id="bbafc-119">이러한 접근 방식을 사용하면 연결 문자열에서 암호를 저장하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-119">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="bbafc-120">자세한 내용은 [SQL Server 보안](../sql-server-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbafc-120">For more information, see [SQL Server Security](../sql-server-security.md).</span></span>  
  
 <span data-ttu-id="bbafc-121">통합 보안을 사용하지 않는 경우에는 연결 문자열에 일반 텍스트 암호를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-121">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="bbafc-122">연결 문자열을 보호하는 가장 좋은 방법은 다음과 같습니다. 아래 항목은 위험 수준에 따라 오름차순으로 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-122">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
- <span data-ttu-id="bbafc-123">통합 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-123">Use integrated security.</span></span>  
  
- <span data-ttu-id="bbafc-124">암호를 사용하여 연결 문자열을 보호하고 연결 문자열의 경유를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-124">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
- <span data-ttu-id="bbafc-125">연결 문자열 대신 노출 기간이 제한되는 <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-125">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="bbafc-126"><xref:System.Data.Linq.DataContext?displayProperty=nameWithType>을 사용하여 LINQ to SQL <xref:System.Data.SqlClient.SqlConnection> 클래스를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-126">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
- <span data-ttu-id="bbafc-127">모든 연결 문자열의 수명과 접근할 수 있는 지점을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="bbafc-127">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbafc-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbafc-128">See also</span></span>

- [<span data-ttu-id="bbafc-129">배경 정보</span><span class="sxs-lookup"><span data-stu-id="bbafc-129">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="bbafc-130">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="bbafc-130">Frequently Asked Questions</span></span>](frequently-asked-questions.md)
