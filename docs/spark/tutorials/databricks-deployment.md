---
title: Databricks에 .NET for Apache Spark 애플리케이션 배포
description: Databricks에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3b00823034cbcb271cb7e169df40122f1144462a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895723"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a>자습서: Databricks에 .NET for Apache Spark 애플리케이션 배포

이 자습서에서는 원 클릭 설정, 간소화된 워크플로 및 협업을 가능하게 하는 대화형 작업 영역이 포함된 Apache Spark 기반 분석 플랫폼인 Azure Databricks를 통해 클라우드에 앱을 배포하는 방법을 설명합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> - Azure Databricks 작업 영역 만들기
> - .NET for Apache Spark 앱 게시
> - Spark 작업 및 Spark 클러스터 만들기
> - Spark 클러스터에서 앱 실행

## <a name="prerequisites"></a>사전 요구 사항

시작하기 전에 다음 작업을 수행합니다.

* Azure 계정이 없으면 [체험 계정](https://azure.microsoft.com/free/dotnet/)을 만듭니다.
* [Azure Portal](https://portal.azure.com/)에 로그인합니다.
* [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro)(.NET for Apache Spark - 10분 이내에 시작하기) 자습서를 완료합니다.

## <a name="create-an-azure-databricks-workspace"></a>Azure Databricks 작업 영역 만들기

> [!Note]
> 이 자습서는 **Azure 평가판 구독**을 사용하여 수행할 수 없습니다.
> 무료 계정이 있는 경우 프로필로 이동하고 구독을 **종량제**로 변경합니다. 자세한 내용은 [Azure 체험 계정](https://azure.microsoft.com/free/dotnet/)을 참조하세요. 그런 다음 [지출 한도를 제거](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit)하고 해당 지역의 vCPU에 대한 [할당량 증가를 요청](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request)합니다. Azure Databricks 작업 영역을 만드는 경우 **평가판(프리미엄-14일 무료 DBU)** 가격 책정 계층을 선택하여 14일간 무료 프리미엄 Azure Databricks DBU를 위한 작업 영역 액세스 권한을 부여할 수 있습니다.

이 섹션에서는 Azure Portal을 사용하여 Azure Databricks 작업 영역을 만듭니다.

1. Azure Portal에서 **리소스 만들기** > **분석** > **Azure Databricks**를 차례로 선택합니다.

   ![Azure Portal에서 Azure Databricks 리소스 만들기](./media/databricks-deployment/create-databricks-resource.png)

2. **Azure Databricks 서비스** 아래에서 Databricks 작업 영역을 만들기 위한 값을 제공합니다.

    |속성  |설명  |
    |---------|---------|
    |**작업 영역 이름**     | Databricks 작업 영역에 대한 이름을 제공합니다.        |
    |**구독**     | 드롭다운에서 Azure 구독을 선택합니다.        |
    |**리소스 그룹**     | 새 리소스 그룹을 만들지, 아니면 기존 그룹을 사용할지 여부를 지정합니다. 리소스 그룹은 Azure 솔루션에 관련된 리소스를 보유하는 컨테이너입니다. 자세한 내용은 [Azure Resource Manager 개요](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)를 참조하세요. |
    |**위치**     | 기본 지역을 선택합니다. 사용 가능한 지역에 대한 자세한 내용은 [지역별 사용 가능한 Azure 서비스](https://azure.microsoft.com/regions/services/)를 참조하세요.        |
    |**가격 책정 계층**     |  **표준**, **프리미엄** 또는 **평가판** 중에서 선택합니다. 이러한 계층에 대한 자세한 내용은 [Databricks 가격 페이지](https://azure.microsoft.com/pricing/details/databricks/)를 참조하세요.       |
    |**Virtual Network**     |   아니요       |

3. **만들기**를 선택합니다. 작업 영역 생성에는 몇 분 정도가 소요됩니다. 작업 영역을 만드는 동안 **알림**에서 배포 상태를 볼 수 있습니다.

## <a name="install-azure-databricks-tools"></a>Azure Databricks 도구 설치

**Databricks CLI**를 사용하여 Azure Databricks 클러스터에 연결하고 로컬 머신에서 파일을 업로드할 수 있습니다. Databricks 클러스터는 DBFS(Databricks 파일 시스템)를 통해 파일에 액세스합니다.

1. Databricks CLI를 사용하려면 Python 3.6 이상이 필요합니다. Python이 이미 설치되어 있는 경우 이 단계를 건너뛰어도 됩니다.

   **Windows:**

   [Windows용 Python을 다운로드](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)합니다.

   **Linux:** 대부분의 Linux 배포에는 Python이 사전 설치되어 있습니다. 다음 명령을 실행하여 설치된 버전을 확인합니다.

   ```bash
   python3 --version
   ```

2. pip를 사용하여 Databricks CLI를 설치합니다. Python 3.4 이상에는 기본적으로 pip가 포함되어 있습니다. Python 3의 pip3을 사용합니다. 다음 명령을 실행합니다.

   ```bash
   pip3 install databricks-cli
   ```

3. Databricks CLI를 설치한 후 새 명령 프롬프트를 열고 `databricks` 명령을 실행합니다. **'databricks'가 내부 또는 외부 명령으로 인식되지 않음 오류**가 표시되면 새 명령 프롬프트를 열었는지 확인합니다.

## <a name="set-up-azure-databricks"></a>Azure Databricks 설정

이제 Databricks CLI가 설치되었으므로 인증 정보를 설정해야 합니다.

1. Databricks CLI 명령 `databricks configure --token`을 실행합니다.

2. 구성 명령을 실행하면 호스트를 입력하라는 메시지가 표시됩니다. 호스트 URL은 **https://<\Location>.azuredatabricks.net** 형식을 사용합니다. 예를 들어 Azure Databricks 서비스를 만드는 동안 **eastus2**를 선택한 경우 호스트는 **https://eastus2.azuredatabricks.net** 이 됩니다.

3. 호스트를 입력하면 토큰을 입력하라는 메시지가 표시됩니다. Azure Portal에서 **작업 영역 시작**을 선택하여 Azure Databricks 작업 영역을 시작합니다.

   ![Azure Databricks 작업 영역 시작](./media/databricks-deployment/launch-databricks-workspace.png)

4. 작업 영역의 홈페이지에서 **사용자 설정**을 선택합니다.

   ![Azure Databricks 작업 영역의 사용자 설정](./media/databricks-deployment/databricks-user-settings.png)

5. 사용자 설정 페이지에서 새 토큰을 생성할 수 있습니다. 생성된 토큰을 복사하여 명령 프롬프트에 다시 붙여넣습니다.

   ![Azure Databricks 작업 영역에서 새 액세스 토큰 생성](./media/databricks-deployment/generate-token.png)

이제 만들어진 Azure Databricks 클러스터에 액세스하고 파일을 DBFS에 업로드할 수 있습니다.

## <a name="download-worker-dependencies"></a>작업자 종속성 다운로드

1. Microsoft.Spark.Worker를 통해 Apache Spark는 사용자가 작성했을 수 있는 UDF(사용자 정의 함수) 등의 앱을 실행합니다. [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz)를 다운로드합니다.

2. *install-worker.sh*는 .NET for Apache Spark 종속 파일을 클러스터의 노드에 복사하는 데 사용할 수 있는 스크립트입니다.

   로컬 컴퓨터에 **install-worker.sh**라는 새 파일을 만들고 GitHub에 있는 [install-worker.sh 콘텐츠](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh)를 붙여넣습니다.

3. *db-init.sh*는 Databricks Spark 클러스터에 종속성을 설치하는 스크립트입니다.

   로컬 컴퓨터에 **db-init.sh**라는 새 파일을 만들고 GitHub에 있는 [db-init.sh 콘텐츠](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)를 붙여넣습니다.

   방금 만든 파일에서 `DOTNET_SPARK_RELEASE` 변수를 `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`로 설정합니다. *db-init.sh* 파일의 나머지 내용은 그대로 둡니다.

> [!Note]
> Windows를 사용하는 경우 *install-worker.sh* 및 *db-init.sh* 스크립트의 줄 끝이 Unix 스타일(LF)인지 확인합니다. Notepad++, Atom 등의 텍스트 편집기를 통해 줄 끝을 변경할 수 있습니다.

## <a name="publish-your-app"></a>앱 게시

[.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro)(.NET for Apache Spark - 10분 이내에 시작하기) 자습서에서 만든 *mySparkApp*을 게시하여 Spark 클러스터가 앱을 실행하는 데 필요한 모든 파일에 액세스할 수 있도록 합니다.

1. 다음 명령을 실행하여 *mySparkApp*을 게시합니다.

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. 다음 작업을 수행하여 게시된 앱 파일을 압축하면 Databricks Spark 클러스터에 쉽게 업로드할 수 있습니다.

   **Windows:**

   mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64로 이동합니다. **게시** 폴더를 마우스 오른쪽 단추로 클릭하고 **보내기 > 압축(zip) 폴더**를 선택합니다. 새 폴더의 이름을 **publish.zip**으로 지정합니다.

   **Linux에서는 다음 명령을 실행합니다.**

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a>파일 업로드

이 섹션에서는 클라우드에서 앱을 실행하는 데 필요한 모든 파일이 클러스터에 포함되도록 여러 개의 파일을 DBFS에 업로드합니다. DBFS에 파일을 업로드할 때는 항상 파일이 있는 컴퓨터의 디렉터리에서 업로드해야 합니다.

1. 다음 명령을 실행하여 *db-init.sh*, *install-worker.sh* 및 *Microsoft.Spark.Worker*를 DBFS에 업로드합니다.

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. 다음 명령을 실행하여 클러스터에서 앱을 실행하는 데 필요한 나머지 파일(압축 게시 폴더, *input.txt* 및 *microsoft-spark-2.4.x-0.3.0.jar*)을 업로드합니다.

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a>작업 만들기

.NET for Apache Spark 작업을 실행하는 데 사용하는 명령인 **spark-submit**을 실행하는 작업을 통해 Azure Databricks에서 앱이 실행됩니다.

1. Azure Databricks 작업 영역에서 **작업** 아이콘, **+ 작업 만들기**를 차례로 선택합니다.

   ![Azure Databricks 작업 만들기](./media/databricks-deployment/create-job.png)

2. 작업 제목을 선택한 다음, **spark-submit 구성**을 선택합니다.

   ![Databricks 작업에 대해 spark-submit 구성](./media/databricks-deployment/configure-spark-submit.png)

3. 작업 구성에 다음 매개 변수를 붙여넣습니다. **확인**을 선택합니다.

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a>클러스터 만들기

1. 작업으로 이동한 다음 **편집**을 선택하여 작업 클러스터를 구성합니다.

2. 클러스터를 **Spark 2.4.1**로 설정합니다. **고급 옵션** > **Init 스크립트**를 선택합니다. Init 스크립트 경로를 `dbfs:/spark-dotnet/db-init.sh`로 설정합니다.

   ![Azure Databricks에서 Spark 클러스터 구성](./media/databricks-deployment/cluster-config.png)

3. **확인**을 선택하여 클러스터 설정을 확인합니다.

## <a name="run-your-app"></a>앱 실행

1. 작업으로 이동한 다음 **지금 실행**을 선택하여 새로 구성된 Spark 클러스터에서 작업을 실행합니다.

2. 작업 클러스터를 만드는 데 몇 분 정도 걸립니다. 클러스터를 만들고 나면 작업이 제출되고 출력을 볼 수 있습니다.

3. 왼쪽 메뉴에서 **클러스터**를 선택한 다음, 작업의 이름과 실행을 선택합니다.

4. **드라이버 로그**를 선택하여 작업의 출력을 살펴봅니다. 앱 실행이 완료되면 시작 로컬 실행과 동일한 단어 개수 테이블이 표준 출력 콘솔에 기록됩니다.

   ![Azure Databricks 작업 출력 테이블](./media/databricks-deployment/table-output.png)

   축하합니다. 클라우드에서 첫 번째 .NET for Apache Spark 애플리케이션을 실행했습니다.

## <a name="clean-up-resources"></a>리소스 정리

Databricks 작업 영역이 더 이상 필요하지 않은 경우 Azure Portal에서 Azure Databricks 리소스를 삭제할 수 있습니다. 또한 리소스 그룹 이름을 선택하여 리소스 그룹 페이지를 연 다음, **리소스 그룹 삭제**를 선택할 수도 있습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 Databricks에 .NET for Apache Spark 애플리케이션을 배포했습니다. Databricks에 대해 자세히 알아보려면 Azure Databricks 설명서를 참조하세요.

> [!div class="nextstepaction"]
> [Azure Databricks 설명서](https://docs.microsoft.com/azure/azure-databricks/)
