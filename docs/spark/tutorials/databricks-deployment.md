---
title: Databricks에 .NET for Apache Spark 애플리케이션 배포
description: Databricks에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 55fa9b42e04a540deb245887d601e6cce0e6e623
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583516"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="3f2d3-103">Databricks에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="3f2d3-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="3f2d3-104">이 자습서에서는 Databricks에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="3f2d3-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3f2d3-106">Microsoft.Spark.Worker 준비</span><span class="sxs-lookup"><span data-stu-id="3f2d3-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="3f2d3-107">Spark .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="3f2d3-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="3f2d3-108">Databricks에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="3f2d3-108">Deploy your app to Databricks</span></span>
> * <span data-ttu-id="3f2d3-109">앱 실행</span><span class="sxs-lookup"><span data-stu-id="3f2d3-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f2d3-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="3f2d3-110">Prerequisites</span></span>

<span data-ttu-id="3f2d3-111">시작하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-111">Before you start, do the following:</span></span>

* <span data-ttu-id="3f2d3-112">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
* <span data-ttu-id="3f2d3-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 로컬 머신에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="3f2d3-114">이 도우미 스크립트는 나중에 .NET for Apache Spark 종속 파일을 Spark 클러스터의 작업자 노드에 복사하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="3f2d3-115">작업자 종속성 준비</span><span class="sxs-lookup"><span data-stu-id="3f2d3-115">Prepare worker dependencies</span></span>

<span data-ttu-id="3f2d3-116">**Microsoft.Spark.Worker**는 Spark 클러스터의 개별 작업자 노드에 있는 백 엔드 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="3f2d3-117">C# UDF(사용자 정의 함수)를 실행하려면 Spark는 .NET CLR를 시작하여 UDF를 실행하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="3f2d3-118">**Microsoft.Spark.Worker**는 이 기능을 사용하도록 설정하는 Spark에 대한 클래스 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="3f2d3-119">클러스터에 배포할 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 릴리스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="3f2d3-120">예를 들어 `netcoreapp2.1`을 사용하는 `.NET for Apache Spark v0.1.0`이 필요한 경우 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="3f2d3-121">클러스터가 액세스할 수 있는 분산 파일 시스템(예: DBFS)에 `Microsoft.Spark.Worker.<release>.tar.gz` 및 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="3f2d3-122">.NET for Apache Spark 앱 준비</span><span class="sxs-lookup"><span data-stu-id="3f2d3-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="3f2d3-123">[시작](get-started.md) 자습서를 따라 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="3f2d3-124">Spark .NET 앱을 자체 포함으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="3f2d3-125">Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-125">You can run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="3f2d3-126">게시된 파일에 대해 `<your app>.zip`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="3f2d3-127">`zip`을 사용하여 Linux에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="3f2d3-128">클러스터가 액세스할 수 있는 분산 파일 시스템(예: DBFS)에 다음을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   * <span data-ttu-id="3f2d3-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: 이 jar은 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지의 일부로 포함되며 앱의 빌드 출력 디렉터리에 공동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="3f2d3-130">각 실행기의 작업 디렉터리에 배치할 파일(예: 모든 작업자에 액세스할 수 있는 공통 데이터 또는 종속성 파일) 또는 어셈블리(예: 앱에서 사용하는 사용자 정의 함수 또는 라이브러리가 포함된 DLL).</span><span class="sxs-lookup"><span data-stu-id="3f2d3-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="3f2d3-131">Databricks에 배포</span><span class="sxs-lookup"><span data-stu-id="3f2d3-131">Deploy to Databricks</span></span>

<span data-ttu-id="3f2d3-132">[Databricks](https://databricks.com)는 Apache Spark를 사용하여 클라우드 기반 빅 데이터 처리를 제공하는 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!NOTE]
> <span data-ttu-id="3f2d3-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) 및 [AWS Databricks](https://databricks.com/aws)는 Linux 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="3f2d3-134">따라서 Databricks에 앱을 배포하려면 앱이 .NET Standard와 호환되며 [.NET Core 컴파일러](https://dotnet.microsoft.com/download)를 사용하여 앱을 컴파일하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="3f2d3-135">Databricks를 사용하면 .NET for Apache Spark 앱을 기존 활성 클러스터에 제출하거나 작업을 시작할 때마다 새 클러스터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="3f2d3-136">이 작업을 수행하려면 .NET for Apache Spark 앱을 제출하기 전에 **Microsoft.Spark.Worker**를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="3f2d3-137">Microsoft.Spark.Worker 배포</span><span class="sxs-lookup"><span data-stu-id="3f2d3-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="3f2d3-138">이 단계는 클러스터에 한 번만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="3f2d3-139">[db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 및 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
)를 로컬 머신에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="3f2d3-140">클러스터에 다운로드하여 설치할 **Microsoft.Spark.Worker** 릴리스를 가리키도록 **db-init.sh**를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="3f2d3-141">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="3f2d3-142">Databricks CLI에 대한 [인증 세부 정보를 설정](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="3f2d3-143">다음 명령을 사용하여 Databricks 클러스터에 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="3f2d3-144">Databricks 작업 영역으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="3f2d3-145">왼쪽 메뉴에서 **클러스터**를 선택한 후 **클러스터 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="3f2d3-146">클러스터를 적절히 구성한 후 **Init 스크립트**를 설정하고 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![스크립트 동작 이미지](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="3f2d3-148">앱 실행</span><span class="sxs-lookup"><span data-stu-id="3f2d3-148">Run your app</span></span>

<span data-ttu-id="3f2d3-149">`set JAR` 또는 `spark-submit`을 사용하여 작업을 Databricks에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="3f2d3-150">JAR 설정 사용</span><span class="sxs-lookup"><span data-stu-id="3f2d3-150">Use Set JAR</span></span>

<span data-ttu-id="3f2d3-151">[JAR 설정](https://docs.databricks.com/user-guide/jobs.html#create-a-job)을 사용하여 기존 활성 클러스터에 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="3f2d3-152">일 회 설정</span><span class="sxs-lookup"><span data-stu-id="3f2d3-152">One-time setup</span></span>

1. <span data-ttu-id="3f2d3-153">Databricks 클러스터로 이동하여 왼쪽 메뉴에서 **작업**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="3f2d3-154">그런 다음, **JAR 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="3f2d3-155">해당하는 `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="3f2d3-156">매개 변수를 적절하게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-156">Set the parameters appropriately.</span></span>

   | <span data-ttu-id="3f2d3-157">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f2d3-157">Parameter</span></span>   | <span data-ttu-id="3f2d3-158">값</span><span class="sxs-lookup"><span data-stu-id="3f2d3-158">Value</span></span>                                                |
   |-------------|------------------------------------------------------|
   | <span data-ttu-id="3f2d3-159">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="3f2d3-159">Main Class</span></span>  | <span data-ttu-id="3f2d3-160">org.apache.spark.deploy.dotnet.DotnetRunner</span><span class="sxs-lookup"><span data-stu-id="3f2d3-160">org.apache.spark.deploy.dotnet.DotnetRunner</span></span>          |
   | <span data-ttu-id="3f2d3-161">인수</span><span class="sxs-lookup"><span data-stu-id="3f2d3-161">Arguments</span></span>   | <span data-ttu-id="3f2d3-162">/dbfs/apps/\<your-app-name>.zip \<your-app-main-class></span><span class="sxs-lookup"><span data-stu-id="3f2d3-162">/dbfs/apps/\<your-app-name>.zip \<your-app-main-class></span></span> |

4. <span data-ttu-id="3f2d3-163">이전 섹션에서 **Init 스크립트**를 만든 기존 클러스터를 가리키도록 **클러스터**를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-163">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="3f2d3-164">앱 게시 및 실행</span><span class="sxs-lookup"><span data-stu-id="3f2d3-164">Publish and run your app</span></span>

1. <span data-ttu-id="3f2d3-165">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)를 사용하여 Databricks 클러스터에 애플리케이션을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-165">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

    ```bash
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

2. <span data-ttu-id="3f2d3-166">이 단계는 앱 어셈블리(예: 종속성과 함께 사용자 정의 함수를 포함하는 DLL)를 각 **Microsoft.Spark.Worker**의 작업 디렉터리에 배치해야 하는 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-166">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   * <span data-ttu-id="3f2d3-167">Databricks 클러스터에 애플리케이션 어셈블리 업로드</span><span class="sxs-lookup"><span data-stu-id="3f2d3-167">Upload your application assemblies to your Databricks cluster</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   * <span data-ttu-id="3f2d3-168">[db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)에서 앱 종속성 섹션의 주석 처리를 제거한 후 앱 종속성 경로를 가리키고 Databricks 클러스터에 업로드하도록 해당 섹션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-168">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```

   * <span data-ttu-id="3f2d3-169">클러스터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-169">Restart your cluster.</span></span>

3. <span data-ttu-id="3f2d3-170">Databricks 작업 영역에서 Databricks 클러스터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="3f2d3-171">**작업**에서 작업을 선택한 후 **지금 실행**을 선택하여 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="3f2d3-172">spark-submit 사용</span><span class="sxs-lookup"><span data-stu-id="3f2d3-172">Use spark-submit</span></span>

<span data-ttu-id="3f2d3-173">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 새 클러스터에 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-173">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="3f2d3-174">[작업을 만들고](https://docs.databricks.com/user-guide/jobs.html) **spark-submit 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-174">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="3f2d3-175">다음 매개 변수를 사용하여 `spark-submit`을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-175">Configure `spark-submit` with the following parameters:</span></span>

    ```bash
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

3. <span data-ttu-id="3f2d3-176">Databricks 작업 영역에서 Databricks 클러스터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-176">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="3f2d3-177">**작업**에서 작업을 선택한 후 **지금 실행**을 선택하여 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-177">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3f2d3-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3f2d3-178">Next steps</span></span>

<span data-ttu-id="3f2d3-179">이 자습서에서는 Databricks에 .NET for Apache Spark 애플리케이션을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-179">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="3f2d3-180">Databricks에 대해 자세히 알아보려면 Azure Databricks 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-180">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3f2d3-181">Azure Databricks 설명서</span><span class="sxs-lookup"><span data-stu-id="3f2d3-181">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
