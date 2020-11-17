---
title: SQL Server에 .NET for Apache Spark 연결
description: .NET for Apache Spark 애플리케이션에서 SQL Server 인스턴스에 연결하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 1fecd796aeefd6c5681c4c2ea623e89f3a5a3c1d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439536"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a>SQL Server에 .NET for Apache Spark 연결

이 문서에서는 [.NET for Apache Spark](https://github.com/dotnet/spark) 애플리케이션에서 SQL Server 인스턴스에 연결하는 방법을 알아봅니다.

## <a name="configure-sql-server-to-grant-your-application-access"></a>애플리케이션에 액세스 권한을 부여하도록 SQL Server 구성

1. SQL Server 인스턴스에 대해 SQL Server 인증을 선택하여 로그인 사용자와 암호를 추가합니다.
2. 다음과 같이 해당 로그인 사용자에게 관련 데이터베이스 수준에서 필요한 권한을 부여합니다.

    ![SQL Server 사용 권한](./media/connect-external-sources/SqlServerAuth.png)

3. SQL Server의 기본 포트인 `1433`이 방화벽에서 허용되는지 확인합니다.
4. SQL 구성 관리자를 열고 아래와 같이 네트워크 구성을 통해 TCP/IP를 사용하도록 설정합니다.

    ![SQL Server TCP/IP 사용](./media/connect-external-sources/SqlServerTCPIP.png)

    위 탭에서 **프로토콜** 아래에 있는 **모두 수신** 값도 확인합니다.

5. `Listen All`이 `No`로 설정된 경우 필요한 모든 IP 주소의 TCP/IP 포트를 1433으로 구성합니다. 또는 IPAll에서 TCP 포트를 설정합니다.

    ![SQL Server TCP/IP 포트](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a>해당 애플리케이션에서 SQL Server에 연결

1. SQL Server용 Microsoft JDBC Driver를 사용하여 해당 애플리케이션을 통해 데이터베이스 연결을 제공합니다([공식 웹 사이트](/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)에서 다운로드).
2. 해당 애플리케이션에서 SQL Server 인스턴스 및 데이터베이스에 연결하려면 다음 구성을 설정합니다.
    1. **connection_url**: SQL Server 인스턴스/데이터베이스에 연결하는 데 사용되는, 다음 형식의 URL입니다.

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. **dbtable**: 액세스할 테이블 이름입니다.
    3. **user**: SQL Server 구성의 1단계에서 설정한 로그인 사용자입니다.
    4. **password**: SQL Server 구성의 1단계에서 설정한 사용자 암호입니다.
3. 아래와 같이 애플리케이션 코드에 위 구성을 사용하여 테이블에서 데이터를 읽어옵니다.

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
