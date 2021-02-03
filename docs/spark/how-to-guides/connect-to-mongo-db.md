---
title: MongoDB에 .NET for Apache Spark 연결
description: .NET for Apache Spark 애플리케이션에서 MongoDB 인스턴스에 연결하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 3889088ce32046f72a9a3392e28a5a36cda4745e
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957847"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a>MongoDB에 .NET for Apache Spark 연결

이 문서에서는 .NET for Apache Spark 애플리케이션에서 MongoDB 인스턴스에 연결하는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 구성 요소

- [데이터베이스 및 일부 컬렉션](https://docs.mongodb.com/manual/core/databases-and-collections/)을 추가하여 MongoDB 서버를 시작하고 실행합니다(로컬 서버를 위해 [관련 커뮤니티 서버](https://www.mongodb.com/try/download/community)를 다운로드하거나, 클라우드 MongoDB 서비스를 위해 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)를 사용해 볼 수 있음).

## <a name="set-up-your-mongodb-instance"></a>MongoDB 인스턴스 설정

.NET for Apache Spark가 MongoDB 인스턴스와 통신하려면 다음을 수행하여 올바르게 설정되었는지 확인해야 합니다.

1. 애플리케이션 연결에 사용할 사용자 이름과 암호를 만들고, mongo 셸을 통해 다음 명령을 사용하여 사용자에게 필요한 권한/역할을 부여합니다.

    ```bash
    use database
    db.createUser(
      {
        user: "mySparkUser",
        pwd: "<password>",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
      }
    )
    ```

2. MongoDB 서버가 연결할 수 있도록 .NET for Apache Spark 애플리케이션이 실행되는 머신의 IP 주소가 허용 목록에 추가되었는지 확인합니다. 작업 방법에 대한 자세한 내용은 [관련 가이드](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/)를 참조할 수 있습니다.

## <a name="configure-your-net-for-apache-spark-application"></a>.NET for Apache Spark 애플리케이션 구성

1. 다음 변수를 설정하여 애플리케이션이 MongoDB 인스턴스와 통신하고 컬렉션에서 읽어오도록 구성합니다.
    1. **authURI**: “필수 MongoDB 인스턴스에 연결할 수 있는 권한을 애플리케이션에 부여하는 연결 문자열”입니다. 관련 형식은 다음과 같습니다.

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. **username**: 이전 섹션의 1단계에서 만든 계정의 사용자 이름
    3. **password**: 만든 사용자 계정의 암호
    4. **cluster_address**: MongoDB 클러스터의 호스트 이름/주소
    5. **database**: 연결할 MongoDB 데이터베이스
    6. **collection**: 읽을 MongoDB 컬렉션. (이 예제에서는 모든 Apache Spark 설치에 제공되는 표준 [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) 예제 파일을 사용합니다.)

2. 아래의 간단한 코드 조각과 같이 `com.mongodb.spark.sql.DefaultSource` 형식의 `spark.Read()`를 사용합니다.

    ```csharp
    class Program
    {
        static void Main()
        {
            var authURI = "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>?retryWrites=true&w=majority";
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Connect to Mongo DB example")
                .Config("spark.mongodb.input.uri", authURI)
                .GetOrCreate();

            DataFrame df = spark.Read().Format("com.mongodb.spark.sql.DefaultSource").Load();
            df.PrintSchema();
            df.Show();
            spark.Stop();
        }
    }
    ```

## <a name="run-your-application"></a>애플리케이션 실행

.NET for Apache Spark 애플리케이션을 실행하려면 sbt 프로젝트의 `build.sbt`에 있는 `libraryDependency`를 사용하여 Spark 프로젝트 빌드 정의의 일부로 `mongo-spark-connector` 모듈을 정의해야 합니다. `spark-submit`(또는 `spark-shell`)와 같은 Spark 환경에서는 `--packages` 명령줄 옵션을 다음과 같이 사용합니다.

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar yourApp.exe
```

> [!NOTE]
> 실행하는 Spark 버전에 따라 패키지 버전을 포함해야 합니다.

표시되는 결과는 아래와 같은 DataFrame(`df`)입니다.

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
