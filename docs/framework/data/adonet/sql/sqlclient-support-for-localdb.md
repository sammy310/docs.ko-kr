---
title: LocalDB에 대한 SqlClient 지원
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824482"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="425af-102">LocalDB에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="425af-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="425af-103">이 문서에서는 LocalDB 데이터베이스에 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-103">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="425af-104">LocalDB는 SQL Server의 경량 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="425af-104">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="425af-105">설명</span><span class="sxs-lookup"><span data-stu-id="425af-105">Remarks</span></span>
  
 <span data-ttu-id="425af-106">LocalDB로 수행할 수 있는 작업을 요약하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="425af-106">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="425af-107">sqllocaldb.exe 또는 app.config 파일을 사용하여 LocalDB 인스턴스를 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-107">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="425af-108">sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터베이스를 추가하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="425af-108">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="425af-109">예: `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="425af-109">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="425af-110">`AttachDBFilename` 연결 문자열 키워드를 사용하여 데이터베이스를 LocalDB 인스턴스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-110">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="425af-111">`AttachDBFilename`을 사용할 때 `Database` 연결 문자열 키워드를 사용하여 데이터베이스 이름을 지정하지 않으면 애플리케이션이 닫힐 때 LocalDB 인스턴스에서 데이터베이스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="425af-111">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="425af-112">연결 문자열에 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-112">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="425af-113">예를 들어 인스턴스 이름이 `myInstance`인 경우 연결 문자열에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="425af-113">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="425af-114">`User Instance=True`는 LocalDB 데이터베이스에 연결할 때 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="425af-114">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="425af-115">LocalDB 설치에 대 한 자세한 내용은 [SQL Server Express localdb](/sql/database-engine/configure-windows/sql-server-express-localdb)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="425af-115">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="425af-116">프로그래밍 방식으로 명명된 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="425af-116">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="425af-117">애플리케이션에서는 명명된 인스턴스를 만들고 다음과 같이 데이터베이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="425af-117">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="425af-118">다음과 같이 app.config 파일에 만들 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-118">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="425af-119">인스턴스의 버전 번호는 LocalDB 설치의 버전 번호와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-119">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- <span data-ttu-id="425af-120">`server` 연결 문자열 키워드를 사용하여 인스턴스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-120">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="425af-121">`server` 연결 문자열 키워드에 지정된 인스턴스 이름은 app.config 파일에 지정된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-121">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="425af-122">`AttachDBFilename` 연결 문자열 키워드를 사용하여 .MDF 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="425af-122">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425af-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="425af-123">See also</span></span>

- [<span data-ttu-id="425af-124">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="425af-124">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="425af-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="425af-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
