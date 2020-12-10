---
title: Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark 설치
description: Azure HDInsight의 Jupyter Notebook에 .NET for Apache Spark를 설치하는 방법을 알아봅니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: ff6b3a64c01fb9148d3abe3d04579233d11a4f73
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599657"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a><span data-ttu-id="758d3-103">Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="758d3-103">Install .NET for Apache Spark on Jupyter Notebooks on Azure HDInsight Spark clusters</span></span>

<span data-ttu-id="758d3-104">이 문서에서는 Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-104">This article teaches you how to install .NET for Apache Spark on Jupyter Notebooks on Azure HDInsight Spark clusters.</span></span> <span data-ttu-id="758d3-105">명령줄과 Azure Portal을 조합하여 Azure HDInsight 클러스터에 .NET for Apache Spark를 배포할 수 있습니다(자세한 내용은 [Azure HDInsight에 .NET for Apache Spark 애플리케이션을 배포하는 방법](../tutorials/hdinsight-deployment.md) 참조). 하지만 Notebook은 보다 대화형이고 반복적인 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-105">You can deploy .NET for Apache Spark on Azure HDInsight clusters through a combination of the command line and the Azure portal (for more information, see [how to deploy a .NET for Apache Spark application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), but notebooks provide a more interactive and iterative experience.</span></span>

<span data-ttu-id="758d3-106">Azure HDInsight 클러스터에는 Jupyter Notebook이 이미 제공되어 있으므로 Jupyter Notebook이 .NET for Apache Spark를 실행하도록 구성하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-106">Azure HDInsight clusters already come with Jupyter Notebooks, so all you have to do is configure the Jupyter Notebooks to run .NET for Apache Spark.</span></span> <span data-ttu-id="758d3-107">Jupyter Notebook에서 .NET for Apache Spark를 사용하려면 C# 코드를 한 줄씩 실행하고 필요한 경우 실행 상태를 유지하기 위해 C# REPL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-107">To use .NET for Apache Spark in your Jupyter Notebooks, a C# REPL is needed to execute your C# code line-by-line and to preserve execution state when necessary.</span></span> <span data-ttu-id="758d3-108">[Try .NET](https://github.com/dotnet/try)이 공식 .NET REPL으로 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-108">[Try .NET](https://github.com/dotnet/try) has been integrated as the official .NET REPL.</span></span>

<span data-ttu-id="758d3-109">Jupyter Notebook 환경을 통해 .NET for Apache Spark를 사용하도록 설정하려면 [Ambari](/azure/hdinsight/hdinsight-hadoop-manage-ambari)를 통해 몇 가지 수동 단계를 수행하고 HDInsight Spark 클러스터에 [스크립트 동작](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-109">To enable .NET for Apache Spark through the Jupyter Notebooks experience, you need to follow a few manual steps through [Ambari](/azure/hdinsight/hdinsight-hadoop-manage-ambari) and submit [script actions](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) on the HDInsight Spark cluster.</span></span>

> [!NOTE]
> <span data-ttu-id="758d3-110">이 기능은 *실험적* 이며 HDInsight Spark 팀에서 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-110">This feature is *experimental* and is not supported by the HDInsight Spark team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="758d3-111">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="758d3-111">Prerequisites</span></span>

<span data-ttu-id="758d3-112">아직 없는 경우 [Azure HDInsight Spark](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-112">If you don't already have one, create an [Azure HDInsight Spark](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) cluster.</span></span>

1. <span data-ttu-id="758d3-113">[Azure Portal](https://portal.azure.com)에서 **+ 리소스 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-113">Visit the [Azure portal](https://portal.azure.com) and select **+ Create a Resource**.</span></span>

1. <span data-ttu-id="758d3-114">새 Azure HDInsight 클러스터 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-114">Create a new Azure HDInsight cluster resource.</span></span> <span data-ttu-id="758d3-115">클러스터를 만드는 동안 **Spark 2.4** 및 **HDI 4.0** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-115">Select **Spark 2.4** and **HDI 4.0** during cluster creation.</span></span>

## <a name="install-net-for-apache-spark"></a><span data-ttu-id="758d3-116">.NET for Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="758d3-116">Install .NET for Apache Spark</span></span>

<span data-ttu-id="758d3-117">Azure Portal에서 이전 단계에서 만든 **HDInsight Spark 클러스터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-117">In the Azure portal, select the **HDInsight Spark cluster** you created in the previous step.</span></span>

### <a name="stop-the-livy-server"></a><span data-ttu-id="758d3-118">Livy 서버 중지</span><span class="sxs-lookup"><span data-stu-id="758d3-118">Stop the Livy server</span></span>

1. <span data-ttu-id="758d3-119">포털에서 **개요** 를 선택하고 **Ambari 홈** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-119">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="758d3-120">메시지가 표시되면 클러스터에 대한 로그인 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-120">If prompted, enter the login credentials for the cluster.</span></span>

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-ambari.png)

2. <span data-ttu-id="758d3-122">왼쪽 탐색 메뉴에서 **Spark2** 를 선택하고 **LIVY FOR SPARK2 SERVER** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-122">Select **Spark2** from the left navigation menu, and select **LIVY FOR SPARK2 SERVER**.</span></span>

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-livyserver.png)

3. <span data-ttu-id="758d3-124">**hn0... host** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-124">Select **hn0... host**.</span></span>

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-host.png)

4. <span data-ttu-id="758d3-126">**Livy for Spark2 Server** 옆에 있는 줄임표를 선택하고 **중지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-126">Select the ellipsis next to **Livy for Spark2 Server** and select **Stop**.</span></span> <span data-ttu-id="758d3-127">메시지가 표시되면 **확인** 을 선택하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-127">When prompted, select **OK** to proceed.</span></span>

   <span data-ttu-id="758d3-128">Livy for Spark2 Server를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-128">Stop Livy for Spark2 Server.</span></span>
   <span data-ttu-id="758d3-129">![Livy 서버 중지](./media/hdinsight-notebook-installation/stop-server.png)</span><span class="sxs-lookup"><span data-stu-id="758d3-129">![Stop Livy Server](./media/hdinsight-notebook-installation/stop-server.png)</span></span>

5. <span data-ttu-id="758d3-130">**hn1... host** 에 대해서도 위 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-130">Repeat the previous steps for **hn1... host**.</span></span>

### <a name="submit-an-hdinsight-script-action"></a><span data-ttu-id="758d3-131">HDInsight 스크립트 동작 제출</span><span class="sxs-lookup"><span data-stu-id="758d3-131">Submit an HDInsight script action</span></span>

1. <span data-ttu-id="758d3-132">`install-interactive-notebook.sh`는 .NET for Apache Spark를 설치하고 Apache Livy 및 sparkmagic을 변경하는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-132">The `install-interactive-notebook.sh` is a script that installs .NET for Apache Spark and makes changes to Apache Livy and sparkmagic.</span></span> <span data-ttu-id="758d3-133">HDInsight에 스크립트 동작을 제출하기 전에 `install-interactive-notebook.sh`를 만들어 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-133">Before you submit a script action to HDInsight, you need to create and upload `install-interactive-notebook.sh`.</span></span>

   <span data-ttu-id="758d3-134">로컬 컴퓨터에 **install-interactive-notebook.sh** 라는 새 파일을 만들고 [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh)의 내용을 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-134">Create a new file named **install-interactive-notebook.sh** in your local computer and paste the contents of [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span></span>

   <span data-ttu-id="758d3-135">이 스크립트를 HDInsight 클러스터에서 액세스할 수 있는 [URI](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions)에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-135">Upload the script to a [URI](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster.</span></span> <span data-ttu-id="758d3-136">예: `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="758d3-136">For example, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span></span>

2. <span data-ttu-id="758d3-137">[HDInsight 스크립트 동작](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)을 사용하여 클러스터에서 `install-interactive-notebook.sh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-137">Run `install-interactive-notebook.sh` on the cluster using [HDInsight Script Actions](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

   <span data-ttu-id="758d3-138">Azure Portal에서 HDI 클러스터로 돌아가서 왼쪽에 있는 옵션에서 **스크립트 동작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-138">Return to your HDI cluster in the Azure portal, and select **Script actions** from the options on the left.</span></span> <span data-ttu-id="758d3-139">HDInsight Spark 클러스터에서 .NET for Apache Spark REPL을 배포하는 스크립트 동작 하나를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-139">You submit one script action to deploy the .NET for Apache Spark REPL on your HDInsight Spark cluster.</span></span> <span data-ttu-id="758d3-140">다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-140">Use the following settings:</span></span>

   |<span data-ttu-id="758d3-141">속성</span><span class="sxs-lookup"><span data-stu-id="758d3-141">Property</span></span>  |<span data-ttu-id="758d3-142">설명</span><span class="sxs-lookup"><span data-stu-id="758d3-142">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="758d3-143">스크립트 유형</span><span class="sxs-lookup"><span data-stu-id="758d3-143">Script type</span></span> | <span data-ttu-id="758d3-144">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="758d3-144">Custom</span></span> |
   | <span data-ttu-id="758d3-145">이름</span><span class="sxs-lookup"><span data-stu-id="758d3-145">Name</span></span> | <span data-ttu-id="758d3-146">*.NET for Apache Spark 대화형 Notebook 환경 설치*</span><span class="sxs-lookup"><span data-stu-id="758d3-146">*Install .NET for Apache Spark Interactive Notebook Experience*</span></span> |
   | <span data-ttu-id="758d3-147">Bash 스크립트 URI</span><span class="sxs-lookup"><span data-stu-id="758d3-147">Bash script URI</span></span> | <span data-ttu-id="758d3-148">`install-interactive-notebook.sh`를 업로드한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-148">The URI to which you uploaded `install-interactive-notebook.sh`.</span></span> |
   | <span data-ttu-id="758d3-149">노드 유형</span><span class="sxs-lookup"><span data-stu-id="758d3-149">Node type(s)</span></span>| <span data-ttu-id="758d3-150">헤드 및 작업자</span><span class="sxs-lookup"><span data-stu-id="758d3-150">Head and Worker</span></span> |
   | <span data-ttu-id="758d3-151">매개 변수</span><span class="sxs-lookup"><span data-stu-id="758d3-151">Parameters</span></span> | <span data-ttu-id="758d3-152">.NET for Apache Spark 버전.</span><span class="sxs-lookup"><span data-stu-id="758d3-152">.NET for Apache Spark version.</span></span> <span data-ttu-id="758d3-153">[.NET for Apache Spark 릴리스](https://github.com/dotnet/spark/releases)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-153">You can check [.NET for Apache Spark releases](https://github.com/dotnet/spark/releases).</span></span> <span data-ttu-id="758d3-154">예를 들어 Sparkdotnet 버전 1.0.0을 설치하려는 경우에는 `1.0.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-154">For example, if you want to install Sparkdotnet version 1.0.0 then it would be `1.0.0`.</span></span>

   <span data-ttu-id="758d3-155">스크립트 동작의 상태 옆에 녹색 확인 표시가 나타나면 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-155">Move to the next step when green checkmarks appear next to the status of the script action.</span></span>

### <a name="start-the-livy-server"></a><span data-ttu-id="758d3-156">Livy 서버 시작</span><span class="sxs-lookup"><span data-stu-id="758d3-156">Start the Livy server</span></span>

<span data-ttu-id="758d3-157">[Livy 서버 중단](#stop-the-livy-server) 섹션에 설명된 지침에 따라 호스트 **hn0** 및 **hn1** 에 대해 Livy for Spark2 Server를 **시작** 합니다(**중단** 이 아님).</span><span class="sxs-lookup"><span data-stu-id="758d3-157">Follow the instructions in the [Stop Livy server](#stop-the-livy-server) section to **Start** (rather than **Stop**) the Livy for Spark2 Server for hosts **hn0** and **hn1**.</span></span>

### <a name="set-up-spark-default-configurations"></a><span data-ttu-id="758d3-158">Spark 기본 구성 설정</span><span class="sxs-lookup"><span data-stu-id="758d3-158">Set up Spark default configurations</span></span>

1. <span data-ttu-id="758d3-159">포털에서 **개요** 를 선택하고 **Ambari 홈** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-159">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="758d3-160">메시지가 표시되면 클러스터에 대한 클러스터 로그인 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-160">If prompted, enter the cluster login credentials for the cluster.</span></span>

2. <span data-ttu-id="758d3-161">**Spark2**, **CONFIGS** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-161">Select **Spark2** and **CONFIGS**.</span></span> <span data-ttu-id="758d3-162">그런 다음 **Custom spark2-defaults** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-162">Then, select **Custom spark2-defaults**.</span></span>

   ![구성 설정](./media/hdinsight-notebook-installation/spark-configs.png)

3. <span data-ttu-id="758d3-164">**속성 추가...** 를 선택하여 Spark 기본 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-164">Select **Add Property...** to add Spark default settings.</span></span>

   ![속성 추가](./media/hdinsight-notebook-installation/add-property.png)

   <span data-ttu-id="758d3-166">세 가지 개별 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-166">There are three individual properties.</span></span> <span data-ttu-id="758d3-167">단일 속성 추가 모드에서 **텍스트** 속성 형식을 사용하여 한 번에 하나씩 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-167">Add them one at a time using the **TEXT** property type in Single property add mode.</span></span> <span data-ttu-id="758d3-168">키/값의 앞뒤에 추가 공백이 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-168">Check that you don't have any extra spaces before or after any of the keys/values.</span></span>

   * <span data-ttu-id="758d3-169">**속성 1**</span><span class="sxs-lookup"><span data-stu-id="758d3-169">**Property 1**</span></span>
       * <span data-ttu-id="758d3-170">키: &ensp;&ensp;`spark.dotnet.shell.command`</span><span class="sxs-lookup"><span data-stu-id="758d3-170">Key:&ensp;&ensp;`spark.dotnet.shell.command`</span></span>
       * <span data-ttu-id="758d3-171">값: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span><span class="sxs-lookup"><span data-stu-id="758d3-171">Value: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span></span>

   * <span data-ttu-id="758d3-172">**속성 2** 이전 스크립트 동작에 포함된 .NET for Apache Spark 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-172">**Property 2** Use the version of .NET for Apache Spark which you had included in the previous script action.</span></span>
       * <span data-ttu-id="758d3-173">키: &ensp;&ensp;`spark.dotnet.packages`</span><span class="sxs-lookup"><span data-stu-id="758d3-173">Key:&ensp;&ensp;`spark.dotnet.packages`</span></span>
       * <span data-ttu-id="758d3-174">값: `["nuget: Microsoft.Spark, 1.0.0", "nuget: Microsoft.Spark.Extensions.Delta, 1.0.0"]`</span><span class="sxs-lookup"><span data-stu-id="758d3-174">Value: `["nuget: Microsoft.Spark, 1.0.0", "nuget: Microsoft.Spark.Extensions.Delta, 1.0.0"]`</span></span>

   * <span data-ttu-id="758d3-175">**속성 3**</span><span class="sxs-lookup"><span data-stu-id="758d3-175">**Property 3**</span></span>
       * <span data-ttu-id="758d3-176">키: &ensp;&ensp;`spark.dotnet.interpreter`</span><span class="sxs-lookup"><span data-stu-id="758d3-176">Key:&ensp;&ensp;`spark.dotnet.interpreter`</span></span>
       * <span data-ttu-id="758d3-177">값: `try`</span><span class="sxs-lookup"><span data-stu-id="758d3-177">Value: `try`</span></span>

   <span data-ttu-id="758d3-178">예를 들어 다음 이미지는 속성 1을 추가하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-178">For example, the following image captures the setting for adding property 1:</span></span>

   ![구성 설정](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   <span data-ttu-id="758d3-180">세 개의 속성을 추가한 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-180">After adding the three properties, select **SAVE**.</span></span> <span data-ttu-id="758d3-181">구성 권장 사항의 경고 화면이 표시되면 **계속 진행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-181">If you see a warning screen of config recommendations, select **PROCEED ANYWAY**.</span></span>

4. <span data-ttu-id="758d3-182">영향을 받는 구성 요소를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-182">Restart affected components.</span></span>

   <span data-ttu-id="758d3-183">새 속성을 추가한 후 변경 내용의 영향을 받는 구성 요소를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-183">After adding the new properties, you need to restart components that were affected by the changes.</span></span> <span data-ttu-id="758d3-184">맨 위에 있는 **다시 시작** 을 선택하고, 드롭다운에서 **영향을 받는 모든 항목을 다시 시작** 합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-184">At the top, select **RESTART**, and then **Restart All Affected** from the drop-down.</span></span>

   ![구성 설정](./media/hdinsight-notebook-installation/restart-affected.png)

   <span data-ttu-id="758d3-186">메시지가 표시되면 **모두 다시 시작 확인** 을 선택하고 계속 진행하고 **확인** 을 클릭하여 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-186">When prompted, select **CONFIRM RESTART ALL** to continue, then click **OK** to finish.</span></span>

## <a name="submit-jobs-through-a-jupyter-notebook"></a><span data-ttu-id="758d3-187">Jupyter Notebook을 통해 작업 제출</span><span class="sxs-lookup"><span data-stu-id="758d3-187">Submit jobs through a Jupyter Notebook</span></span>

<span data-ttu-id="758d3-188">이전 단계를 완료한 후 Jupyter Notebook을 통해 .NET for Apache Spark 작업을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-188">After finishing the previous steps, you can now submit your .NET for Apache Spark jobs through Jupyter Notebooks.</span></span>

1. <span data-ttu-id="758d3-189">새 .NET for Apache Spark Notebook을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-189">Create a new .NET for Apache Spark notebook.</span></span> <span data-ttu-id="758d3-190">Azure Portal의 HDI 클러스터에서 Jupyter Notebook을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-190">Launch a Jupyter Notebook from your HDI cluster in the Azure portal.</span></span>

   ![Jupyter Notebook 시작](./media/hdinsight-notebook-installation/launch-notebook.png)

   <span data-ttu-id="758d3-192">그런 다음 **새로 만들기** >  **.NET Spark(C#)** 를 선택하여 Notebook을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-192">Then, select **New** > **.NET Spark (C#)** to create a notebook.</span></span>

   ![Jupyter 노트북](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. <span data-ttu-id="758d3-194">.NET for Apache Spark를 사용하여 작업을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-194">Submit jobs using .NET for Apache Spark.</span></span>

   <span data-ttu-id="758d3-195">다음 코드 조각을 사용하여 데이터 프레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-195">Use the following code snippet to create a DataFrame:</span></span>

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Spark 작업 제출](./media/hdinsight-notebook-installation/create-df.png)

   <span data-ttu-id="758d3-197">다음 코드 조각을 사용하여 UDF(사용자 정의 함수)를 등록하고 데이터 프레임에 UDF를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="758d3-197">Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:</span></span>

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Spark 작업 제출](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a><span data-ttu-id="758d3-199">다음 단계</span><span class="sxs-lookup"><span data-stu-id="758d3-199">Next steps</span></span>

* [<span data-ttu-id="758d3-200">Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="758d3-200">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="758d3-201">HDInsight 설명서</span><span class="sxs-lookup"><span data-stu-id="758d3-201">HDInsight Documentation</span></span>](/azure/hdinsight/)
