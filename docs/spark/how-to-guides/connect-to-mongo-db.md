---
title: MongoDB에 .NET for Apache Spark 연결
description: .NET for Apache Spark 애플리케이션에서 MongoDB 인스턴스에 연결하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 928cc8e3559e13af66268f3d1b3766cf2df9041f
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223972"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a><span data-ttu-id="a3273-103">MongoDB에 .NET for Apache Spark 연결</span><span class="sxs-lookup"><span data-stu-id="a3273-103">Connect .NET for Apache Spark to MongoDB</span></span>

<span data-ttu-id="a3273-104">이 문서에서는 .NET for Apache Spark 애플리케이션에서 MongoDB 인스턴스에 연결하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-104">In this article, you learn how to connect to a MongoDB instance from your .NET for Apache Spark application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3273-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a3273-105">Prerequisites</span></span>

1. <span data-ttu-id="a3273-106">[데이터베이스 및 일부 컬렉션](https://docs.mongodb.com/manual/core/databases-and-collections/)을 추가하여 MongoDB 서버를 시작하고 실행합니다(로컬 서버를 위해 [관련 커뮤니티 서버](https://www.mongodb.com/try/download/community)를 다운로드하거나, 클라우드 MongoDB 서비스를 위해 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)를 사용해 볼 수 있음).</span><span class="sxs-lookup"><span data-stu-id="a3273-106">Have a MongoDB server up and running with a [database and some collection](https://docs.mongodb.com/manual/core/databases-and-collections/) added to it (Download [this community server](https://www.mongodb.com/try/download/community) for a local server or you can try [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for a cloud MongoDB service.)</span></span>

## <a name="set-up-your-mongodb-instance"></a><span data-ttu-id="a3273-107">MongoDB 인스턴스 설정</span><span class="sxs-lookup"><span data-stu-id="a3273-107">Set up your MongoDB instance</span></span>

<span data-ttu-id="a3273-108">.NET for Apache Spark가 MongoDB 인스턴스와 통신하려면 다음을 수행하여 올바르게 설정되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-108">In order to get .NET for Apache Spark to talk to your MongoDB instance you need to make sure it is set up correctly by doing the following:</span></span>

1. <span data-ttu-id="a3273-109">애플리케이션 연결에 사용할 사용자 이름과 암호를 만들고, mongo 셸을 통해 다음 명령을 사용하여 사용자에게 필요한 권한/역할을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-109">Create a username and password for your application to connect through, and give the user the necessary permissions/roles using the following command through mongo shell:</span></span>

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

2. <span data-ttu-id="a3273-110">MongoDB 서버가 연결할 수 있도록 .NET for Apache Spark 애플리케이션을 실행하는 머신의 IP 주소가 허용 목록에 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-110">Make sure the IP address of the machine your .NET for Apache Spark application is running on is whitelisted for the MongoDB server to be able to connect to.</span></span> <span data-ttu-id="a3273-111">작업 방법에 대한 자세한 내용은 [관련 가이드](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-111">You can refer to [this guide](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) to learn how to do that.</span></span>

## <a name="configure-your-net-for-apache-spark-application"></a><span data-ttu-id="a3273-112">.NET for Apache Spark 애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="a3273-112">Configure your .NET for Apache Spark application</span></span>

1. <span data-ttu-id="a3273-113">다음 변수를 설정하여 애플리케이션이 MongoDB 인스턴스와 통신하고 컬렉션에서 읽어오도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-113">Have the following variables set to configure your application to talk to the MongoDB instance and read from a collection.</span></span>
    1. <span data-ttu-id="a3273-114">**authURI** : “필수 MongoDB 인스턴스에 연결할 수 있는 권한을 애플리케이션에 부여하는 연결 문자열”입니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-114">**authURI** : "Connection string authorizing your application to connect to the required MongoDB instance".</span></span> <span data-ttu-id="a3273-115">관련 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-115">The format for that is as follows:</span></span>

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. <span data-ttu-id="a3273-116">**username** : 이전 섹션의 1단계에서 만든 계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="a3273-116">**username** : Username of the account you created in Step 1 of the previous section</span></span>
    3. <span data-ttu-id="a3273-117">**password** : 만든 사용자 계정의 암호</span><span class="sxs-lookup"><span data-stu-id="a3273-117">**password** : Password of the user account created</span></span>
    4. <span data-ttu-id="a3273-118">**cluster_address** : MongoDB 클러스터의 호스트 이름/주소</span><span class="sxs-lookup"><span data-stu-id="a3273-118">**cluster_address** : hostname/address of your MongoDB cluster</span></span>
    5. <span data-ttu-id="a3273-119">**database** : 연결할 MongoDB 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="a3273-119">**database** : The MongoDB database you want to connect to</span></span>
    6. <span data-ttu-id="a3273-120">**collection** : 읽을 MongoDB 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="a3273-120">**collection** : The MongoDB collection you want to read.</span></span> <span data-ttu-id="a3273-121">(이 예제에서는 모든 Apache Spark 설치에 제공되는 표준 [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) 예제 파일을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="a3273-121">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.)</span></span>

2. <span data-ttu-id="a3273-122">아래의 간단한 코드 조각과 같이 `com.mongodb.spark.sql.DefaultSource` 형식의 `spark.Read()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-122">Use the `com.mongodb.spark.sql.DefaultSource` format is `spark.Read()` as shown below in a simple code snippet:</span></span>

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

## <a name="run-your-application"></a><span data-ttu-id="a3273-123">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a3273-123">Run your application</span></span>

<span data-ttu-id="a3273-124">.NET for Apache Spark 애플리케이션을 실행하려면 sbt 프로젝트의 `build.sbt`에 있는 `libraryDependency`를 사용하여 Spark 프로젝트 빌드 정의의 일부로 `mongo-spark-connector` 모듈을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-124">In order to run your .NET for Apache Spark application, you should define the `mongo-spark-connector` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="a3273-125">`spark-submit`(또는 `spark-shell`)와 같은 Spark 환경에서는 `--packages` 명령줄 옵션을 다음과 같이 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-125">For Spark environments such as `spark-submit` (or `spark-shell`) you should use the `--packages` command-line option like so:</span></span>

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<version>.jar yourApp.exe
```

> [!NOTE]
> <span data-ttu-id="a3273-126">실행하는 Spark 버전에 따라 패키지 버전을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-126">Make sure to include the package version in accordance with the version of Spark being run.</span></span>

<span data-ttu-id="a3273-127">표시되는 결과는 아래와 같은 DataFrame(`df`)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3273-127">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
