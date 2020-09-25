---
title: LocalDB에 대한 SqlClient 지원
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203425"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="f5299-102">LocalDB에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="f5299-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="f5299-103">SQL Server 코드 이름 Denali부터는 LocalDB라고 부르는 SQL Server의 경량 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="f5299-104">이 항목에서는 LocalDB 인스턴스에 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5299-105">설명</span><span class="sxs-lookup"><span data-stu-id="f5299-105">Remarks</span></span>  

 <span data-ttu-id="f5299-106">LocalDB 설치 및 LocalDB 인스턴스 구성 방법을 포함하여 LocalDB에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5299-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="f5299-107">LocalDB로 수행할 수 있는 작업을 요약하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="f5299-108">sqllocaldb.exe 또는 app.config 파일을 사용하여 LocalDB 인스턴스를 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="f5299-109">sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터베이스를 추가하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="f5299-110">예: `sqlcmd -S (localdb)\myinst`</span><span class="sxs-lookup"><span data-stu-id="f5299-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="f5299-111">`AttachDBFilename` 연결 문자열 키워드를 사용하여 데이터베이스를 LocalDB 인스턴스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="f5299-112">`AttachDBFilename`을 사용할 때 `Database` 연결 문자열 키워드를 사용하여 데이터베이스 이름을 지정하지 않으면 애플리케이션이 닫힐 때 LocalDB 인스턴스에서 데이터베이스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="f5299-113">연결 문자열에 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="f5299-114">예를 들어 인스턴스 이름이 `myInstance`인 경우 연결 문자열에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="f5299-115">`User Instance=True`는 LocalDB 데이터베이스에 연결할 때 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="f5299-116">[Microsoft SQL Server 2012 기능 팩](https://www.microsoft.com/download/en/details.aspx?id=29065)에서 LocalDB를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="f5299-117">sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터를 수정할 경우 SQL Server 2012의 sqlcmd가 필요합니다. sqlcmd는 SQL Server 2012 기능 팩에서도 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="f5299-118">프로그래밍 방식으로 명명된 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="f5299-118">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="f5299-119">애플리케이션에서는 명명된 인스턴스를 만들고 다음과 같이 데이터베이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-119">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="f5299-120">다음과 같이 app.config 파일에 만들 LocalDB 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="f5299-121">인스턴스의 버전 번호는 LocalDB 설치의 버전 번호와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="f5299-122">`server` 연결 문자열 키워드를 사용하여 인스턴스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="f5299-123">`server` 연결 문자열 키워드에 지정된 인스턴스 이름은 app.config 파일에 지정된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="f5299-124">`AttachDBFilename` 연결 문자열 키워드를 사용하여 .MDF 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5299-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5299-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5299-125">See also</span></span>

- [<span data-ttu-id="f5299-126">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5299-126">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="f5299-127">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f5299-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
