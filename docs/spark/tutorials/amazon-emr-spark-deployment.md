---
title: Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포
description: Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dd1cfdf12266b55d9dbc0210479b89ba68c59a38
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688074"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="0d3a3-103">Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="0d3a3-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="0d3a3-104">이 자습서에서는 Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="0d3a3-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)은 AWS에서 빅 데이터 프레임워크 실행을 간소화하는 관리형 클러스터 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

<span data-ttu-id="0d3a3-106">이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0d3a3-107">Microsoft.Spark.Worker 준비</span><span class="sxs-lookup"><span data-stu-id="0d3a3-107">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="0d3a3-108">Spark .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="0d3a3-108">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="0d3a3-109">Amazon EMR Spark에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="0d3a3-109">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="0d3a3-110">앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-110">Run your app</span></span>

> [!Note]
> <span data-ttu-id="0d3a3-111">AWS EMR Spark는 Linux 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-111">AWS EMR Spark is Linux-based.</span></span> <span data-ttu-id="0d3a3-112">따라서 AWS EMR Spark에 앱을 배포하려면 앱이 .NET Standard와 호환되는지, .NET Core 컴파일러를 사용하여 앱을 컴파일하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-112">Therefore, if you are interested in deploying your app to AWS EMR Spark, make sure your app is .NET Standard compatible and that you use .NET Core compiler to compile your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d3a3-113">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d3a3-113">Prerequisites</span></span>

<span data-ttu-id="0d3a3-114">시작하기 전에 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-114">Before you start, do the following:</span></span>

* <span data-ttu-id="0d3a3-115">[AWS CLI](https://aws.amazon.com/cli/)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-115">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="0d3a3-116">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 로컬 머신에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-116">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="0d3a3-117">이 도우미 스크립트는 나중에 .NET for Apache Spark 종속 파일을 Spark 클러스터의 작업자 노드에 복사하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-117">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="0d3a3-118">작업자 종속성 준비</span><span class="sxs-lookup"><span data-stu-id="0d3a3-118">Prepare worker dependencies</span></span>

<span data-ttu-id="0d3a3-119">**Microsoft.Spark.Worker** 는 Spark 클러스터의 개별 작업자 노드에 있는 백 엔드 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-119">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="0d3a3-120">C# UDF(사용자 정의 함수)를 실행하려면 Spark는 .NET CLR를 시작하여 UDF를 실행하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-120">When you want to execute a C# UDF (User-Defined Function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="0d3a3-121">**Microsoft.Spark.Worker** 는 이 기능을 사용하도록 설정하는 Spark에 대한 클래스 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-121">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="0d3a3-122">클러스터에 배포할 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 릴리스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-122">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="0d3a3-123">예를 들어 `netcoreapp3.1`을 사용하는 `.NET for Apache Spark v1.0.0`이 필요한 경우 [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-123">For example, if you want `.NET for Apache Spark v1.0.0` using `netcoreapp3.1`, you'd download [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span>

2. <span data-ttu-id="0d3a3-124">클러스터가 액세스할 수 있는 분산 파일 시스템(예: S3)에 `Microsoft.Spark.Worker.<release>.tar.gz` 및 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-124">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="0d3a3-125">.NET for Apache Spark 앱 준비</span><span class="sxs-lookup"><span data-stu-id="0d3a3-125">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0d3a3-126">[시작](get-started.md) 자습서를 따라 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-126">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="0d3a3-127">Spark .NET 앱을 자체 포함으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-127">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="0d3a3-128">Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-128">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="0d3a3-129">게시된 파일에 대해 `<your app>.zip`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-129">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="0d3a3-130">`zip`을 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-130">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="0d3a3-131">클러스터가 액세스할 수 있는 분산 파일 시스템(예: S3)에 다음 항목을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-131">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="0d3a3-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: 이 jar은 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지의 일부로 포함되며 앱의 빌드 출력 디렉터리에 공동 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="0d3a3-133">각 실행기의 작업 디렉터리에 배치할 파일(예: 모든 작업자에 액세스할 수 있는 공통 데이터 또는 종속성 파일) 또는 어셈블리(예: 앱에서 사용하는 사용자 정의 함수 또는 라이브러리가 포함된 DLL).</span><span class="sxs-lookup"><span data-stu-id="0d3a3-133">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="0d3a3-134">Amazon EMR Spark에 배포</span><span class="sxs-lookup"><span data-stu-id="0d3a3-134">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="0d3a3-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html)은 AWS에서 빅 데이터 프레임워크 실행을 간소화하는 관리형 클러스터 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="0d3a3-136">Amazon EMR Spark는 Linux 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-136">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="0d3a3-137">따라서 Amazon EMR Spark에 앱을 배포하려면 앱이 .NET Standard와 호환되며 [.NET Core 컴파일러](https://dotnet.microsoft.com/download)를 사용하여 앱을 컴파일하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-137">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="0d3a3-138">Microsoft.Spark.Worker 배포</span><span class="sxs-lookup"><span data-stu-id="0d3a3-138">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="0d3a3-139">이 단계는 클러스터를 만들 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-139">This step is only required at cluster creation.</span></span>

<span data-ttu-id="0d3a3-140">[부트스트랩 작업](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)을 사용하여 클러스터를 만드는 동안 `install-worker.sh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-140">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="0d3a3-141">AWS CLI를 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-141">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="0d3a3-142">앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-142">Run your app</span></span>

<span data-ttu-id="0d3a3-143">Amazon EMR Spark에서 앱을 실행하는 두 가지 방법은 spark-submit 및 Amazon EMR Steps입니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-143">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="0d3a3-144">spark-submit 사용</span><span class="sxs-lookup"><span data-stu-id="0d3a3-144">Use spark-submit</span></span>

<span data-ttu-id="0d3a3-145">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Amazon EMR Spark에 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-145">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="0d3a3-146">클러스터의 노드 중 하나로 `ssh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-146">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="0d3a3-147">`spark-submit`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-147">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="0d3a3-148">Amazon EMR Steps 사용</span><span class="sxs-lookup"><span data-stu-id="0d3a3-148">Use Amazon EMR Steps</span></span>

<span data-ttu-id="0d3a3-149">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html)는 EMR 클러스터에 설치된 Spark 프레임워크에 작업을 제출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-149">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="0d3a3-150">AWS CLI를 사용하여 Linux에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-150">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="0d3a3-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0d3a3-151">Next steps</span></span>

<span data-ttu-id="0d3a3-152">이 자습서에서는 Amazon EMR Spark에 .NET for Apache Spark 애플리케이션을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-152">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="0d3a3-153">.NET for Apache Spark 예제 프로젝트를 진행하려면 GitHub로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3a3-153">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0d3a3-154">.NET for Apache Spark 샘플</span><span class="sxs-lookup"><span data-stu-id="0d3a3-154">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
