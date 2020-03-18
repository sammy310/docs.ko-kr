---
title: Azure HDInsight에 Apache Spark 작업의 .NET 제출
description: Apache Livy 및 spark-submit을 사용하여 Azure HDInsight에 Apache Spark 작업의 .NET을 제출하는 방법에 대해 알아봅니다.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 83359f7f613b500a4ce121ce1612cda0ad1191ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185793"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="eeabf-103">Azure HDInsight에 Apache Spark 작업의 .NET 제출</span><span class="sxs-lookup"><span data-stu-id="eeabf-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="eeabf-104">Apache Spark 작업의 .NET을 HDInsight에 배포하는 방법에는 두 가지 방법(`spark-submit` 및 Apache Livy)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="eeabf-105">spark-submit을 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="eeabf-105">Deploy using spark-submit</span></span>

<span data-ttu-id="eeabf-106">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Azure HDInsight에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="eeabf-107">Azure Portal에서 해당 HDInsight Spark 클러스터로 이동한 다음, **SSH + 클러스터 로그인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="eeabf-108">ssh 로그인 정보를 복사하고 터미널에 로그인을 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="eeabf-109">클러스터를 만드는 동안 설정한 암호를 사용하여 클러스터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="eeabf-110">Ubuntu 및 Spark에 오신 것을 환영하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="eeabf-111">**spark-submit** 명령을 사용하여 HDInsight 클러스터에서 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="eeabf-112">예제 스크립트의 **mycontainer** 및 **mystorageaccount**를 Blob 컨테이너 및 스토리지 계정의 실제 이름으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="eeabf-113">또한 배포에서 `microsoft-spark-2.3.x-0.6.0.jar`를 사용하는 해당 jar 파일로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="eeabf-114">`2.3.x`은(는) Apache Spark 버전을 나타내며 `0.6.0`은(는) [.NET for Apache Spark 작업자](https://github.com/dotnet/spark/releases)의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="eeabf-115">Apache Livy를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="eeabf-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="eeabf-116">Apache Spark REST API인 [Apache Livy](https://livy.incubator.apache.org/)를 사용하여 Azure HDInsight Spark 클러스터에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="eeabf-117">자세한 내용은 [Apache Livy를 사용한 원격 작업](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eeabf-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="eeabf-118">`curl`을 사용하여 Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeabf-118">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="eeabf-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="eeabf-119">Next steps</span></span>

* [<span data-ttu-id="eeabf-120">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="eeabf-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="eeabf-121">Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="eeabf-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="eeabf-122">HDInsight 설명서</span><span class="sxs-lookup"><span data-stu-id="eeabf-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
