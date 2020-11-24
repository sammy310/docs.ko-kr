---
title: Databricks에 .NET for Apache Spark 작업 제출
description: Set Jar 및 spark-submit을 사용하여 Databricks에 Apache Spark 작업의 .NET을 제출하는 방법에 대해 알아봅니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4d37383ccb3c9b311e0fbd0ada195ac20113e505
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688204"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a><span data-ttu-id="e115b-103">Databricks에 .NET for Apache Spark 작업 제출</span><span class="sxs-lookup"><span data-stu-id="e115b-103">Submit a .NET for Apache Spark job to Databricks</span></span>

<span data-ttu-id="e115b-104">Databricks 클러스터에서 .NET for Apache Spark 작업을 실행할 수 있지만 기본적으로 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-104">You can run your .NET for Apache Spark jobs on Databricks clusters, but it is not available out-of-the-box.</span></span> <span data-ttu-id="e115b-105">.NET for Apache Spark 작업을 Databricks에 배포하는 방법은 두 가지(`spark-submit` 및 Set Jar)입니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-105">There are two ways to deploy your .NET for Apache Spark job to Databricks: `spark-submit` and Set Jar.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="e115b-106">spark-submit을 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="e115b-106">Deploy using spark-submit</span></span>

<span data-ttu-id="e115b-107">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Databricks에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-107">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="e115b-108">`spark-submit`을 사용하여 요청 시 만들어지는 클러스터에만 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-108">`spark-submit` allows submission only to a cluster that gets created on-demand.</span></span>

1. <span data-ttu-id="e115b-109">Databricks 작업 영역으로 이동하여 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-109">Navigate to your Databricks Workspace and create a job.</span></span> <span data-ttu-id="e115b-110">작업 제목을 선택한 다음, **spark-submit 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-110">Choose a title for your job, and then select **Configure spark-submit**.</span></span> <span data-ttu-id="e115b-111">작업 구성에 다음 매개 변수를 붙여넣은 후 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-111">Paste the following parameters in the job configuration, then select **Confirm**.</span></span>

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > <span data-ttu-id="e115b-112">특정 파일 및 구성을 기반으로 위 매개 변수의 콘텐츠를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-112">Update the contents of the above parameter based on your specific files and configuration.</span></span> <span data-ttu-id="e115b-113">예를 들어 DBFS에 업로드한 Microsoft.Spark jar 파일 버전을 참조하고 적절한 앱 이름과 게시된 앱 zip 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-113">For instance, reference the version of the Microsoft.Spark jar file that you uploaded to DBFS, and use the appropriate name of your app and published app zip file.</span></span>

2. <span data-ttu-id="e115b-114">작업으로 이동한 다음 **편집** 을 선택하여 작업 클러스터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-114">Navigate to your job and select **Edit** to configure your job's cluster.</span></span> <span data-ttu-id="e115b-115">배포에 사용할 Apache Spark 버전에 따라 Databricks Runtime 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-115">Set the Databricks Runtime Version based on the version of Apache Spark you wish to use in your deployment.</span></span> <span data-ttu-id="e115b-116">그런 다음 **고급 옵션 > Init 스크립트** 를 선택하고 Init 스크립트 경로를 `dbfs:/spark-dotnet/db-init.sh`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-116">Then select **Advanced Options > Init Scripts**, and set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span> <span data-ttu-id="e115b-117">**확인** 을 선택하여 클러스터 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-117">Select **Confirm** to confirm your cluster settings.</span></span>

3. <span data-ttu-id="e115b-118">작업으로 이동한 다음 **지금 실행** 을 선택하여 새로 구성된 Spark 클러스터에서 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-118">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span> <span data-ttu-id="e115b-119">작업 클러스터를 만드는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-119">It takes a few minutes for the job's cluster to be created.</span></span> <span data-ttu-id="e115b-120">클러스터를 만들면 작업이 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-120">Once it is created, your job will be submitted.</span></span> <span data-ttu-id="e115b-121">Databricks 작업 영역의 왼쪽 메뉴에서 **클러스터** 를 선택하여 출력을 확인한 다음, **드라이버 로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-121">You can view the output by selecting **Clusters** from the left menu of your Databricks workspace, then select **Driver Logs**.</span></span>

## <a name="deploy-using-set-jar"></a><span data-ttu-id="e115b-122">Set Jar를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="e115b-122">Deploy using Set Jar</span></span>

<span data-ttu-id="e115b-123">또는 Databricks 작업 영역에서 [Set Jar](/azure/databricks/jobs#--create-a-job)를 사용하여 Databricks에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-123">Alternatively, you can use [Set Jar](/azure/databricks/jobs#--create-a-job) in your Databricks workspace to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="e115b-124">*Set Jar* 를 사용하여 기존 활성 클러스터에 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-124">*Set Jar* allows job submission to an existing active cluster.</span></span>

### <a name="one-time-setup"></a><span data-ttu-id="e115b-125">일 회 설정</span><span class="sxs-lookup"><span data-stu-id="e115b-125">One-time setup</span></span>

1. <span data-ttu-id="e115b-126">Databricks 클러스터로 이동하여 왼쪽 메뉴에서 **작업**, **Set JAR** 를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-126">Navigate to your Databricks cluster and select **Jobs** from the left-side menu, followed by **Set JAR**.</span></span>

2. <span data-ttu-id="e115b-127">해당하는 `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-127">Upload the appropriate `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`.</span></span>

3. <span data-ttu-id="e115b-128">`<your-app-name>` 대신 게시한 실행 파일의 올바른 이름을 포함하도록 다음 매개 변수를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-128">Modify the following parameters to include the correct name for the executable that you published in place of `<your-app-name>`:</span></span>

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. <span data-ttu-id="e115b-129">init 스크립트를 이미 설정한 기존 클러스터를 가리키도록 클러스터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-129">Configure the cluster to point to an existing cluster for which you have already set the init script.</span></span>

### <a name="publish-and-run-your-app"></a><span data-ttu-id="e115b-130">앱 게시 및 실행</span><span class="sxs-lookup"><span data-stu-id="e115b-130">Publish and run your app</span></span>

1. <span data-ttu-id="e115b-131">앱을 게시했고 애플리케이션 코드가 `SparkSession.Stop()`을 사용하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-131">Ensure you have published your app, and that your application code does not use `SparkSession.Stop()`.</span></span>

2. <span data-ttu-id="e115b-132">[Databricks CLI](/azure/databricks/dev-tools/databricks-cli)를 사용하여 Databricks 클러스터에 애플리케이션을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-132">Use [Databricks CLI](/azure/databricks/dev-tools/databricks-cli) to upload your application to your Databricks cluster.</span></span> <span data-ttu-id="e115b-133">예를 들어 다음 명령을 사용하여 클러스터에 게시된 앱을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-133">For example, use the following command to upload your published app to your cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. <span data-ttu-id="e115b-134">앱에 사용자 정의 함수가 있는 경우 앱 어셈블리(예: 종속성과 함께 사용자 정의 함수를 포함하는 DLL)는 각 *Microsoft.Spark.Worker* 의 작업 디렉터리에 배치해야 하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-134">If you have any user-defined functions in your app, the app assemblies, such as DLLs that contain user-defined functions along with their dependencies, need to be placed in the working directory of each *Microsoft.Spark.Worker*.</span></span>

    <span data-ttu-id="e115b-135">Databricks 클러스터에 애플리케이션 어셈블리 업로드:</span><span class="sxs-lookup"><span data-stu-id="e115b-135">Upload your application assemblies to your Databricks cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    <span data-ttu-id="e115b-136">[db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)에서 앱 종속성 섹션의 주석 처리를 제거한 후 앱 종속성 경로를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-136">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path.</span></span> <span data-ttu-id="e115b-137">그런 다음, 업데이트된 *db-init.sh* 를 클러스터에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-137">Then, upload the updated *db-init.sh* to your cluster:</span></span>

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. <span data-ttu-id="e115b-138">**Databricks 클러스터 > 작업 > [작업 이름] > 지금 실행** 으로 이동하여 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e115b-138">Navigate to **Databricks cluster > Jobs > [Job-name] > Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e115b-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e115b-139">Next steps</span></span>

* [<span data-ttu-id="e115b-140">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="e115b-140">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="e115b-141">Databricks에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="e115b-141">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="e115b-142">Azure Databricks 설명서</span><span class="sxs-lookup"><span data-stu-id="e115b-142">Azure Databricks Documentation</span></span>](/azure/azure-databricks/)
