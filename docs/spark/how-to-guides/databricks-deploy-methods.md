---
title: Databricks에 .NET for Apache Spark 작업 제출
description: Set Jar 및 spark-submit을 사용하여 Databricks에 Apache Spark 작업의 .NET을 제출하는 방법에 대해 알아봅니다.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: bebd170a689d8ae56aa6c55486d70354da2437ea
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617771"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a>Databricks에 .NET for Apache Spark 작업 제출

Databricks 클러스터에서 .NET for Apache Spark 작업을 실행할 수 있지만 기본적으로 사용할 수는 없습니다. .NET for Apache Spark 작업을 Databricks에 배포하는 방법은 두 가지(`spark-submit` 및 Set Jar)입니다.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="deploy-using-spark-submit"></a>spark-submit을 사용하여 배포

[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Databricks에 .NET for Apache Spark 작업을 제출할 수 있습니다. `spark-submit`을 사용하여 요청 시 만들어지는 클러스터에만 제출할 수 있습니다.

1. Databricks 작업 영역으로 이동하여 작업을 만듭니다. 작업 제목을 선택한 다음, **spark-submit 구성**을 선택합니다. 작업 구성에 다음 매개 변수를 붙여넣은 후 **확인**을 선택합니다.

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > 특정 파일 및 구성을 기반으로 위 매개 변수의 콘텐츠를 업데이트합니다. 예를 들어 DBFS에 업로드한 Microsoft.Spark jar 파일 버전을 참조하고 적절한 앱 이름과 게시된 앱 zip 파일을 사용합니다.

2. 작업으로 이동한 다음 **편집**을 선택하여 작업 클러스터를 구성합니다. 배포에 사용할 Apache Spark 버전에 따라 Databricks Runtime 버전을 설정합니다. 그런 다음 **고급 옵션 > Init 스크립트**를 선택하고 Init 스크립트 경로를 `dbfs:/spark-dotnet/db-init.sh`로 설정합니다. **확인**을 선택하여 클러스터 설정을 확인합니다.

3. 작업으로 이동한 다음 **지금 실행**을 선택하여 새로 구성된 Spark 클러스터에서 작업을 실행합니다. 작업 클러스터를 만드는 데 몇 분 정도 걸립니다. 클러스터를 만들면 작업이 제출됩니다. Databricks 작업 영역의 왼쪽 메뉴에서 **클러스터**를 선택하여 출력을 확인한 다음, **드라이버 로그**를 선택합니다.

## <a name="deploy-using-set-jar"></a>Set Jar를 사용하여 배포

또는 Databricks 작업 영역에서 [Set Jar](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job)를 사용하여 Databricks에 .NET for Apache Spark 작업을 제출할 수 있습니다. *Set Jar*를 사용하여 기존 활성 클러스터에 작업을 제출할 수 있습니다.

### <a name="one-time-setup"></a>일 회 설정

1. Databricks 클러스터로 이동하여 왼쪽 메뉴에서 **작업**, **Set JAR**를 차례로 선택합니다.

2. 해당하는 `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` 파일을 업로드합니다.

3. `<your-app-name>` 대신 게시한 실행 파일의 올바른 이름을 포함하도록 다음 매개 변수를 수정합니다.

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. init 스크립트를 이미 설정한 기존 클러스터를 가리키도록 클러스터를 구성합니다.

### <a name="publish-and-run-your-app"></a>앱 게시 및 실행

1. 앱을 게시했고 애플리케이션 코드가 `SparkSession.Stop()`을 사용하지 않는지 확인합니다.

2. [Databricks CLI](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli)를 사용하여 Databricks 클러스터에 애플리케이션을 업로드합니다. 예를 들어 다음 명령을 사용하여 클러스터에 게시된 앱을 업로드합니다.

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. 앱에 사용자 정의 함수가 있는 경우 앱 어셈블리(예: 종속성과 함께 사용자 정의 함수를 포함하는 DLL)는 각 *Microsoft.Spark.Worker*의 작업 디렉터리에 배치해야 하는 경우에만 필요합니다.

    Databricks 클러스터에 애플리케이션 어셈블리 업로드:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)에서 앱 종속성 섹션의 주석 처리를 제거한 후 앱 종속성 경로를 가리킵니다. 그런 다음, 업데이트된 *db-init.sh*를 클러스터에 업로드합니다.

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. **Databricks 클러스터 > 작업 > [작업 이름] > 지금 실행**으로 이동하여 작업을 실행합니다.

## <a name="next-steps"></a>다음 단계

* [.NET for Apache Spark 시작](../tutorials/get-started.md)
* [Databricks에 .NET for Apache Spark 애플리케이션 배포](../tutorials/databricks-deployment.md)
* [Azure Databricks 설명서](https://docs.microsoft.com/azure/azure-databricks/)
