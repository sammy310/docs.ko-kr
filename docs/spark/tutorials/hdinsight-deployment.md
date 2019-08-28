---
title: Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포
description: HDInsight에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4769c194520790ce217d46d1d3197b20742d4f1a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "69576950"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="4bb91-103">Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="4bb91-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="4bb91-104">이 자습서에서는 Azure HDInsight에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="4bb91-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="4bb91-106">Microsoft.Spark.Worker 준비</span><span class="sxs-lookup"><span data-stu-id="4bb91-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="4bb91-107">Spark .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="4bb91-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="4bb91-108">Azure HDInsight에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="4bb91-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="4bb91-109">앱 실행</span><span class="sxs-lookup"><span data-stu-id="4bb91-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bb91-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4bb91-110">Prerequisites</span></span>

<span data-ttu-id="4bb91-111">시작하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-111">Before you start, do the following:</span></span>

* <span data-ttu-id="4bb91-112">[Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="4bb91-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 로컬 머신에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="4bb91-114">이 도우미 스크립트는 나중에 .NET for Apache Spark 종속 파일을 Spark 클러스터의 작업자 노드에 복사하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="4bb91-115">작업자 종속성 준비</span><span class="sxs-lookup"><span data-stu-id="4bb91-115">Prepare worker dependencies</span></span>

<span data-ttu-id="4bb91-116">**Microsoft.Spark.Worker**는 Spark 클러스터의 개별 작업자 노드에 있는 백 엔드 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="4bb91-117">C# UDF(사용자 정의 함수)를 실행하려면 Spark는 .NET CLR를 시작하여 UDF를 실행하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="4bb91-118">**Microsoft.Spark.Worker**는 이 기능을 사용하도록 설정하는 Spark에 대한 클래스 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="4bb91-119">클러스터에 배포할 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 릴리스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="4bb91-120">예를 들어 `netcoreapp2.1`을 사용하는 `.NET for Apache Spark v0.1.0`이 필요한 경우 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="4bb91-121">클러스터가 액세스할 수 있는 분산 파일 시스템(예: HDFS, WASB, ADLS)에 `Microsoft.Spark.Worker.<release>.tar.gz` 및 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="4bb91-122">.NET for Apache Spark 앱 준비</span><span class="sxs-lookup"><span data-stu-id="4bb91-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="4bb91-123">[시작](get-started.md) 자습서를 따라 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="4bb91-124">Spark .NET 앱을 자체 포함으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="4bb91-125">Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="4bb91-126">게시된 파일에 대해 `<your app>.zip`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="4bb91-127">`zip`을 사용하여 Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="4bb91-128">클러스터가 액세스할 수 있는 분산 파일 시스템(예: HDFS, WASB, ADLS)에 다음을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="4bb91-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: 이 jar은 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지의 일부로 포함되며 앱의 빌드 출력 디렉터리에 공동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="4bb91-130">각 실행기의 작업 디렉터리에 배치할 파일(예: 모든 작업자에 액세스할 수 있는 공통 데이터 또는 종속성 파일) 또는 어셈블리(예: `app`에서 사용하는 사용자 정의 함수 또는 라이브러리가 포함된 DLL).</span><span class="sxs-lookup"><span data-stu-id="4bb91-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="4bb91-131">Azure HDInsight Spark에 배포</span><span class="sxs-lookup"><span data-stu-id="4bb91-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="4bb91-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview)는 사용자가 Azure에서 Spark 클러스터를 시작하고 구성할 수 있는 클라우드에 있는 Apache Spark의 Microsoft 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="4bb91-133">따라서 HDInsight Spark 클러스터를 사용하여 [Azure Storage](https://azure.microsoft.com/services/storage/) 또는 [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2)에 저장된 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="4bb91-134">Azure HDInsight Spark는 Linux 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="4bb91-135">Azure HDInsight Spark에 앱을 배포하려면 앱이 .NET Standard와 호환되며 [.NET Core 컴파일러](https://dotnet.microsoft.com/download)를 사용하여 앱을 컴파일하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="4bb91-136">Microsoft.Spark.Worker 배포</span><span class="sxs-lookup"><span data-stu-id="4bb91-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="4bb91-137">이 단계는 클러스터에 한 번만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="4bb91-138">[HDInsight 스크립트 동작](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)을 사용하여 클러스터에서 `install-worker.sh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="4bb91-139">설정</span><span class="sxs-lookup"><span data-stu-id="4bb91-139">Setting</span></span>|<span data-ttu-id="4bb91-140">값</span><span class="sxs-lookup"><span data-stu-id="4bb91-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="4bb91-141">스크립트 유형</span><span class="sxs-lookup"><span data-stu-id="4bb91-141">Script type</span></span>|<span data-ttu-id="4bb91-142">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4bb91-142">Custom</span></span>|
|<span data-ttu-id="4bb91-143">name</span><span class="sxs-lookup"><span data-stu-id="4bb91-143">Name</span></span>|<span data-ttu-id="4bb91-144">Microsoft.Spark.Worker 설치</span><span class="sxs-lookup"><span data-stu-id="4bb91-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="4bb91-145">Bash 스크립트 URI</span><span class="sxs-lookup"><span data-stu-id="4bb91-145">Bash script URI</span></span>|<span data-ttu-id="4bb91-146">`install-worker.sh`를 업로드한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="4bb91-147">예를 들면 `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="4bb91-148">노드 유형</span><span class="sxs-lookup"><span data-stu-id="4bb91-148">Node type(s)</span></span>|<span data-ttu-id="4bb91-149">작업자</span><span class="sxs-lookup"><span data-stu-id="4bb91-149">Worker</span></span>|
|<span data-ttu-id="4bb91-150">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4bb91-150">Parameters</span></span>|<span data-ttu-id="4bb91-151">`install-worker.sh`에 대한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="4bb91-152">예를 들어 `install-worker.sh`를 Azure Data Lake Gen 2에 업로드한 경우 `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![스크립트 동작 이미지](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="4bb91-154">앱 실행</span><span class="sxs-lookup"><span data-stu-id="4bb91-154">Run your app</span></span>

<span data-ttu-id="4bb91-155">`spark-submit` 또는 Apache Livy를 사용하여 Azure HDInsight에 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="4bb91-156">spark-submit 사용</span><span class="sxs-lookup"><span data-stu-id="4bb91-156">Use spark-submit</span></span>

<span data-ttu-id="4bb91-157">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Azure HDInsight에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="4bb91-158">클러스터의 헤드 노드 중 하나로 `ssh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="4bb91-159">`spark-submit`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="4bb91-160">Apache Livy 사용</span><span class="sxs-lookup"><span data-stu-id="4bb91-160">Use Apache Livy</span></span>

<span data-ttu-id="4bb91-161">Apache Spark REST API인 [Apache Livy](https://livy.incubator.apache.org/)를 사용하여 Azure HDInsight Spark 클러스터에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="4bb91-162">자세한 내용은 [Apache Livy를 사용한 원격 작업](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bb91-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="4bb91-163">`curl`을 사용하여 Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="4bb91-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4bb91-164">Next steps</span></span>

<span data-ttu-id="4bb91-165">이 자습서에서는 Azure HDInsight에 .NET for Apache Spark 애플리케이션을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb91-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="4bb91-166">HDInsight에 대해 자세히 알아보려면 Azure HDInsight 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bb91-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4bb91-167">Azure HDInsight 설명서</span><span class="sxs-lookup"><span data-stu-id="4bb91-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
