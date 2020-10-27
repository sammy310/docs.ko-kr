---
title: SQL Server에 .NET for Apache Spark 연결
description: .NET for Apache Spark 애플리케이션에서 SQL Server 인스턴스에 연결하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: b20710000d8717b5df238aa9a782371fbe586037
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224033"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a><span data-ttu-id="70bd8-103">SQL Server에 .NET for Apache Spark 연결</span><span class="sxs-lookup"><span data-stu-id="70bd8-103">Connect .NET for Apache Spark to SQL Server</span></span>

<span data-ttu-id="70bd8-104">이 문서에서는 [.NET for Apache Spark](https://github.com/dotnet/spark) 애플리케이션에서 SQL Server 인스턴스에 연결하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-104">In this article, you learn how to connect to an SQL server instance from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

## <a name="configure-sql-server-to-grant-your-application-access"></a><span data-ttu-id="70bd8-105">애플리케이션에 액세스 권한을 부여하도록 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="70bd8-105">Configure SQL Server to grant your application access</span></span>

1. <span data-ttu-id="70bd8-106">SQL Server 인스턴스에 대해 SQL Server 인증을 선택하여 로그인 사용자와 암호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-106">Add a login user and password choosing SQL Server authentication to your SQL Server instance.</span></span>
2. <span data-ttu-id="70bd8-107">다음과 같이 해당 로그인 사용자에게 관련 데이터베이스 수준에서 필요한 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-107">Give that login user necessary permissions at the relevant database level as shown below:</span></span>

    ![SQL Server 사용 권한](./media/connect-external-sources/SqlServerAuth.png)

3. <span data-ttu-id="70bd8-109">SQL Server의 기본 포트인 `1433`이 방화벽에서 허용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-109">Make sure the default port for SQL Server `1433` is allowed through the firewall.</span></span>
4. <span data-ttu-id="70bd8-110">SQL 구성 관리자를 열고 아래와 같이 네트워크 구성을 통해 TCP/IP를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-110">Open SQL configure manager to enable TCP/IP through the network configuration as shown below:</span></span>

    ![SQL Server TCP/IP 사용](./media/connect-external-sources/SqlServerTCPIP.png)

    <span data-ttu-id="70bd8-112">위 탭에서 **프로토콜** 아래에 있는 **모두 수신** 값도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-112">Also note the value of **Listen All** in above tab under **Protocol** .</span></span>

5. <span data-ttu-id="70bd8-113">`Listen All`이 `No`로 설정된 경우 필요한 모든 IP 주소의 TCP/IP 포트를 1433으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-113">Configure the TCP/IP port to 1433 for all required IP addresses if the `Listen All` is set to `No`.</span></span> <span data-ttu-id="70bd8-114">또는 IPAll에서 TCP 포트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-114">Otherwise, set the TCP Port in IPAll.</span></span>

    ![SQL Server TCP/IP 포트](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a><span data-ttu-id="70bd8-116">해당 애플리케이션에서 SQL Server에 연결</span><span class="sxs-lookup"><span data-stu-id="70bd8-116">Connect to SQL Server from your application</span></span>

1. <span data-ttu-id="70bd8-117">SQL Server용 Microsoft JDBC Driver를 사용하여 해당 애플리케이션을 통해 데이터베이스 연결을 제공합니다([공식 웹 사이트](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)에서 다운로드).</span><span class="sxs-lookup"><span data-stu-id="70bd8-117">Use the Microsoft JDBC Driver for SQL Server to provide database connectivity through your application (download from [this official website](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span></span>
2. <span data-ttu-id="70bd8-118">해당 애플리케이션에서 SQL Server 인스턴스 및 데이터베이스에 연결하려면 다음 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-118">Set the following configurations to connect to the SQL server instance and database from your application:</span></span>
    1. <span data-ttu-id="70bd8-119">**connection_url** : SQL Server 인스턴스/데이터베이스에 연결하는 데 사용되는, 다음 형식의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-119">**connection_url** : This is the URL used to connect to the SQL server instance/database and has the following format:</span></span>

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. <span data-ttu-id="70bd8-120">**dbtable** : 액세스할 테이블 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-120">**dbtable** : Name of table being accessed.</span></span>
    3. <span data-ttu-id="70bd8-121">**user** : SQL Server 구성의 1단계에서 설정한 로그인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-121">**user** : Login user set up in Step 1 of configuring the SQL server.</span></span>
    4. <span data-ttu-id="70bd8-122">**password** : SQL Server 구성의 1단계에서 설정한 사용자 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-122">**password** : Password of user set up in Step 1 of configuring the SQL server.</span></span>
3. <span data-ttu-id="70bd8-123">아래와 같이 애플리케이션 코드에 위 구성을 사용하여 테이블에서 데이터를 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="70bd8-123">Use the above configuration in your application code to read the data from a table as shown below:</span></span>

    ```csharp
    static void Main()
    {
        SparkSession spark = SparkSession
            .Builder()
            .AppName("Connect to SQL Server")
            .GetOrCreate();

        string connection_url = "<URL to connect to SQL server instance>";
        string dbtable = "<database table to access>";
        string user = "<Login user name>";
        string password = "<Login user password>";

        DataFrame jdbcDF = spark.Read()
            .Format("jdbc")
            .Option("driver", "com.microsoft.sqlserver.jdbc.SQLServerDriver")
            .Option("url", connection_url)
            .Option("dbtable", dbtable)
            .Option("user", user)
            .Option("password", password).Load();
        jdbcDF.Show(); // Displays the content of the SQL table as a DataFrame
    }
    ```
