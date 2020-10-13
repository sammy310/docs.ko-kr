---
title: Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포
description: HDInsight에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 살펴봅니다.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8ef1429d265c87347bb8771dc01b319fcb9e84d0
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955372"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>자습서: Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포

이 자습서에서는 Azure HDInsight 클러스터를 통해 .NET for Apache Spark 앱을 클라우드에 배포하는 방법을 설명합니다. Hdinsight의 Spark 클러스터는 Azure Storage 및 Azure Data Lake Storage와 호환되므로, HDInsight를 사용하면 Azure에서 Spark 클러스터를 보다 쉽게 만들고 구성할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * Azure Storage Explorer를 사용하여 해당 스토리지 계정 액세스
> * Azure HDInsight 클러스터 만들기
> * .NET for Apache Spark 앱 게시
> * HDInsight 스크립트 동작 만들기 및 실행
> * HDInsight 클러스터에서 .NET for Apache Spark 앱 실행

## <a name="prerequisites"></a>사전 요구 사항

시작하기 전에 다음 작업을 수행합니다.

* Azure 구독이 아직 없는 경우 [체험 계정](https://azure.microsoft.com/free/dotnet/)을 만듭니다.
* [Azure Portal](https://portal.azure.com/)에 로그인합니다.
* [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409) 또는 [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) 컴퓨터에 Azure Storage Explorer를 설치합니다.
* [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro)(.NET for Apache Spark - 10분 이내에 시작하기) 자습서를 완료합니다.

## <a name="access-your-storage-accounts"></a>해당 스토리지 계정 액세스

1. Azure Storage Explorer를 엽니다.

2. 왼쪽 메뉴에서 **계정 추가**를 선택하고 Azure 계정에 로그인합니다.

    ![Storage Explorer에서 Azure 계정에 로그인합니다.](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   로그인하면 보유한 모든 스토리지 계정과 해당 스토리지 계정에 업로드한 모든 리소스가 표시됩니다.

## <a name="create-an-hdinsight-cluster"></a>HDInsight 클러스터 만들기

> [!IMPORTANT]
> HDInsight 클러스터에 대한 청구는 사용하지 않는 경우에도 분 단위로 비례 배분됩니다. 사용한 후에 클러스터를 삭제해야 합니다. 자세한 내용은 이 자습서의 [리소스 정리](#clean-up-resources) 섹션을 참조하세요.

1. [Azure Portal](https://portal.azure.com)을 방문합니다.

2. **+ 리소스 만들기**를 선택합니다. **Analytics** 범주에서 **HDInsight**를 선택합니다.

    ![Azure Portal에서 HDInsight 리소스 만들기](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. **기본**에서 다음 값을 입력합니다.

    |속성  |설명  |
    |---------|---------|
    |구독  | 드롭다운에서 활성 Azure 구독 중 하나를 선택합니다. |
    |리소스 그룹 | 새 리소스 그룹을 만들지, 아니면 기존 그룹을 사용할지 여부를 지정합니다. 리소스 그룹은 Azure 솔루션에 관련된 리소스를 보유하는 컨테이너입니다. |
    |클러스터 이름 | HDInsight Spark 클러스터에 이름을 지정합니다.|
    |위치   | 리소스 그룹의 위치를 선택합니다. 템플릿에서는 기본 클러스터 스토리지뿐만 아니라 클러스터를 만드는 데 이 위치를 사용합니다. |
    |클러스터 유형| 클러스터 유형으로 **Spark**를 선택합니다.|
    |클러스터 버전|클러스터 유형을 선택하면 이 필드가 기본 버전으로 자동으로 채워집니다. Spark 2.3 또는 2.4 버전을 선택합니다.|
    |클러스터 로그인 사용자 이름| 클러스터 로그인 사용자 이름을 입력합니다.  기본 이름은 *admin*입니다. |
    |클러스터 로그인 암호| 로그인 암호를 입력합니다. |
    |SSH(보안 셸) 사용자 이름| SSH 사용자 이름을 입력합니다. 기본적으로 이 계정에는 *클러스터 로그인 사용자 이름* 계정과 동일한 암호를 공유합니다. |

4. 완료되면 **다음: Storage >>** 를 선택하여 **Storage** 페이지를 계속합니다. **스토리지**에서 다음 값을 입력합니다.

    |속성  |설명  |
    |---------|---------|
    |기본 스토리지 유형|기본값 **Azure Storage**를 사용합니다.|
    |선택 방법|기본값 **목록에서 선택**을 사용합니다.|
    |기본 스토리지 계정|구독과 해당 구독 내의 활성 스토리지 계정 중 하나를 선택합니다.|
    |컨테이너|이 컨테이너는 클러스터가 클라우드에서 앱을 실행하기 위해 파일을 찾는 해당 스토리지 계정의 특정 Blob 컨테이너입니다. 사용 가능한 이름을 임의로 지정할 수 있습니다.|

5. **검토 + 만들기**에서 **만들기**를 선택합니다. 클러스터를 만드는 데 약 20분이 걸립니다. 클러스터를 만들어야 다음 단계를 계속 진행할 수 있습니다.

## <a name="publish-your-app"></a>앱 게시

[.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro)(.NET for Apache Spark - 10분 이내에 시작하기) 자습서에서 만든 *mySparkApp*을 게시하여 Spark 클러스터가 앱을 실행하는 데 필요한 모든 파일에 액세스할 수 있도록 합니다.

1. 다음 명령을 실행하여 *mySparkApp*을 게시합니다.

   **Windows:**

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   **Linux:**

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. 다음 작업을 수행하여 게시된 앱 파일을 압축하면 HDInsight 클러스터에 쉽게 업로드할 수 있습니다.

   **Windows:**

   *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*로 이동합니다. **게시** 폴더를 마우스 오른쪽 단추로 클릭하고 **보내기 > 압축(zip) 폴더**를 선택합니다. 새 폴더의 이름을 **publish.zip**으로 지정합니다.

   **Linux에서는 다음 명령을 실행합니다.**

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a>Azure에 파일 업로드

Azure Storage Explorer를 사용하여 클러스터 스토리지로 선택한 Blob 컨테이너에 다음 5개 파일을 업로드합니다.

* Microsoft.Spark.Worker
* install-worker.sh
* publish.zip
* microsoft-spark-2.3.x-0.3.0.jar
* input.txt.

1. Azure Storage Explorer를 열고 왼쪽 메뉴에서 해당 스토리지 계정으로 이동합니다. 해당 스토리지 계정의 **Blob 컨테이너**에서 클러스터의 Blob 컨테이너로 드릴다운합니다.

2. *Microsoft.Spark.Worker*를 통해 Apache Spark는 사용자가 작성했을 수 있는 UDF(사용자 정의 함수) 등의 앱을 실행합니다. [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz)를 다운로드합니다. Azure Storage Explorer에서 **업로드**를 선택하여 작업자를 업로드합니다.

   ![Azure Storage Explorer에 파일 업로드](./media/hdinsight-deployment/upload-files-to-storage.png)

3. *install-worker.sh*는 .NET for Apache Spark 종속 파일을 클러스터의 노드에 복사하는 데 사용할 수 있는 스크립트입니다.

   로컬 컴퓨터에 **install-worker.sh**라는 새 파일을 만들고 GitHub에 있는 [install-worker.sh 콘텐츠](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh)를 붙여넣습니다. Blob 컨테이너에 *install-worker.sh*를 업로드합니다.

4. 클러스터에 앱의 게시된 파일이 포함된 publish.zip 파일이 필요합니다. 게시된 폴더인 **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**로 이동하여 **publish.zip**을 찾습니다. Blob 컨테이너에 *publish.zip*을 업로드합니다.

5. 클러스터에 jar 파일로 패키지된 애플리케이션 코드가 필요합니다. 게시된 폴더인 **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**로 이동하여 **microsoft-spark-2.3.x-0.3.0.jar**을 찾습니다. Blob 컨테이너에 jar 파일을 업로드합니다.

   여러 개의 .jar 파일이 있을 수 있습니다(Spark 버전 2.3.x 및 2.4.x의 경우). 클러스터를 만드는 동안 선택한 Spark 버전과 일치하는 .jar 파일을 선택해야 합니다. 예를 들어 클러스터를 만드는 동안 Spark 2.3.2를 선택한 경우 *microsoft-spark-2.3.x-0.3.0.jar*을 선택합니다.

6. 클러스터에 앱에 대한 입력이 필요합니다. **mySparkApp** 디렉터리로 이동하여 **input.txt**를 찾습니다. Blob 컨테이너의 **user/sshuser** 디렉터리에 입력 파일을 업로드합니다. ssh를 통해 클러스터에 연결하며, 클러스터는 이 폴더에서 해당 입력을 찾습니다. *input.txt* 파일은 특정 디렉터리로 업로드되는 유일한 파일입니다.

## <a name="run-the-hdinsight-script-action"></a>HDInsight 스크립트 동작 실행

클러스터가 실행 중이고 Azure에 파일을 업로드했으면, 클러스터에서 **install-worker.sh** 스크립트를 실행합니다.

1. Azure Portal에서 해당 HDInsight Spark 클러스터로 이동한 다음, **스크립트 동작**을 선택합니다.

2. **+ 새로운 항목 제출**을 선택하고 다음 값을 지정합니다.

   |속성  |설명  |
   |---------|---------|
   | 스크립트 유형 |사용자 지정|
   | 이름 | 작업자 설치|
   | Bash 스크립트 URI |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> 이 URI를 확인하려면 Azure Storage Explorer에서 install-worker.sh를 마우스 오른쪽 단추로 클릭하고 속성을 선택합니다. |
   | 노드 유형| 작업자|
   | 매개 변수 | azure </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> /usr/local/bin

3. **만들기**를 선택하여 스크립트를 제출합니다.

## <a name="run-your-app"></a>앱 실행

1. Azure Portal에서 해당 HDInsight Spark 클러스터로 이동한 다음, **SSH + 클러스터 로그인**을 선택합니다.

2. ssh 로그인 정보를 복사하고 터미널에 로그인을 붙여넣습니다. 클러스터를 만드는 동안 설정한 암호를 사용하여 클러스터에 로그인합니다. Ubuntu 및 Spark에 오신 것을 환영하는 메시지가 표시됩니다.

3. **spark-submit** 명령을 사용하여 HDInsight 클러스터에서 앱을 실행합니다. 예제 스크립트의 **mycontainer** 및 **mystorageaccount**를 Blob 컨테이너 및 스토리지 계정의 실제 이름으로 바꾸어야 합니다.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   앱이 실행되면 시작 로컬 실행과 동일한 단어 개수 테이블이 콘솔에 기록됩니다. 축하합니다. 클라우드에서 첫 번째 .NET for Apache Spark 애플리케이션을 실행했습니다.

## <a name="clean-up-resources"></a>리소스 정리

HDInsight는 Azure Storage에 데이터를 저장하므로, 사용하지 않을 때는 클러스터를 삭제해도 안전합니다. HDInsight 클러스터를 사용하지 않는 기간에도 요금이 청구됩니다. 클러스터에 대한 요금이 스토리지에 대한 요금보다 몇 배 더 많기 때문에, 클러스터를 사용하지 않을 때는 삭제하는 것이 경제적인 면에서 더 합리적입니다.

또한 리소스 그룹 이름을 선택하여 리소스 그룹 페이지를 연 다음, **리소스 그룹 삭제**를 선택할 수도 있습니다. 리소스 그룹을 삭제하여 HDInsight Spark 클러스터와 기본 스토리지 계정을 삭제합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 Azure HDInsight에 .NET for Apache Spark 애플리케이션을 배포했습니다. HDInsight에 대해 자세히 알아보려면 Azure HDInsight 설명서를 참조하세요.

> [!div class="nextstepaction"]
> [Azure HDInsight 설명서](/azure/hdinsight/)
