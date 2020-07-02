---
title: Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포
description: Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6cf26044693c5d923d11e1bbc72232e7009fe73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618261"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="23296-103">Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="23296-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="23296-104">이 자습서에서는 Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="23296-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="23296-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="23296-106">Microsoft.Spark.Worker 준비</span><span class="sxs-lookup"><span data-stu-id="23296-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="23296-107">Spark .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="23296-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="23296-108">Amazon EMR Spark에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="23296-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="23296-109">앱 실행</span><span class="sxs-lookup"><span data-stu-id="23296-109">Run your app</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="23296-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="23296-110">Prerequisites</span></span>

<span data-ttu-id="23296-111">시작하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-111">Before you start, do the following:</span></span>

* <span data-ttu-id="23296-112">[AWS CLI](https://aws.amazon.com/cli/)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="23296-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 로컬 머신에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="23296-114">이 도우미 스크립트는 나중에 .NET for Apache Spark 종속 파일을 Spark 클러스터의 작업자 노드에 복사하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="23296-115">작업자 종속성 준비</span><span class="sxs-lookup"><span data-stu-id="23296-115">Prepare worker dependencies</span></span>

<span data-ttu-id="23296-116">**Microsoft.Spark.Worker**는 Spark 클러스터의 개별 작업자 노드에 있는 백 엔드 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="23296-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="23296-117">C# UDF(사용자 정의 함수)를 실행하려면 Spark는 .NET CLR를 시작하여 UDF를 실행하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="23296-118">**Microsoft.Spark.Worker**는 이 기능을 사용하도록 설정하는 Spark에 대한 클래스 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="23296-119">클러스터에 배포할 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 릴리스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="23296-120">예를 들어 `netcoreapp2.1`을 사용하는 `.NET for Apache Spark v0.1.0`이 필요한 경우 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="23296-121">클러스터가 액세스할 수 있는 분산 파일 시스템(예: S3)에 `Microsoft.Spark.Worker.<release>.tar.gz` 및 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="23296-122">.NET for Apache Spark 앱 준비</span><span class="sxs-lookup"><span data-stu-id="23296-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="23296-123">[시작](get-started.md) 자습서를 따라 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="23296-124">Spark .NET 앱을 자체 포함으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="23296-125">Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="23296-126">게시된 파일에 대해 `<your app>.zip`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="23296-127">`zip`을 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="23296-128">클러스터가 액세스할 수 있는 분산 파일 시스템(예: S3)에 다음 항목을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="23296-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: 이 jar은 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지의 일부로 포함되며 앱의 빌드 출력 디렉터리에 공동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="23296-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="23296-130">각 실행기의 작업 디렉터리에 배치할 파일(예: 모든 작업자에 액세스할 수 있는 공통 데이터 또는 종속성 파일) 또는 어셈블리(예: 앱에서 사용하는 사용자 정의 함수 또는 라이브러리가 포함된 DLL).</span><span class="sxs-lookup"><span data-stu-id="23296-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="23296-131">Amazon EMR Spark에 배포</span><span class="sxs-lookup"><span data-stu-id="23296-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="23296-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)은 AWS에서 빅 데이터 프레임워크 실행을 간소화하는 관리형 클러스터 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="23296-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="23296-133">Amazon EMR Spark는 Linux 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="23296-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="23296-134">따라서 Amazon EMR Spark에 앱을 배포하려면 앱이 .NET Standard와 호환되며 [.NET Core 컴파일러](https://dotnet.microsoft.com/download)를 사용하여 앱을 컴파일하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="23296-135">Microsoft.Spark.Worker 배포</span><span class="sxs-lookup"><span data-stu-id="23296-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="23296-136">이 단계는 클러스터를 만들 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="23296-137">[부트스트랩 작업](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)을 사용하여 클러스터를 만드는 동안 `install-worker.sh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="23296-138">AWS CLI를 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-138">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="23296-139">앱 실행</span><span class="sxs-lookup"><span data-stu-id="23296-139">Run your app</span></span>

<span data-ttu-id="23296-140">Amazon EMR Spark에서 앱을 실행하는 두 가지 방법은 spark-submit 및 Amazon EMR Steps입니다.</span><span class="sxs-lookup"><span data-stu-id="23296-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="23296-141">spark-submit 사용</span><span class="sxs-lookup"><span data-stu-id="23296-141">Use spark-submit</span></span>

<span data-ttu-id="23296-142">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Amazon EMR Spark에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23296-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="23296-143">클러스터의 노드 중 하나로 `ssh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="23296-144">`spark-submit`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="23296-145">Amazon EMR Steps 사용</span><span class="sxs-lookup"><span data-stu-id="23296-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="23296-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html)는 EMR 클러스터에 설치된 Spark 프레임워크에 작업을 제출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23296-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="23296-147">AWS CLI를 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="23296-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="23296-148">Next steps</span></span>

<span data-ttu-id="23296-149">이 자습서에서는 Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="23296-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="23296-150">.NET for Apache Spark 예제 프로젝트를 진행하려면 GitHub로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23296-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="23296-151">.NET for Apache Spark 샘플</span><span class="sxs-lookup"><span data-stu-id="23296-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
