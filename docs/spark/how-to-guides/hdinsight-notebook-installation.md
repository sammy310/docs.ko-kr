---
title: Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark 설치
description: Azure HDInsight의 Jupyter Notebook에 .NET for Apache Spark를 설치하는 방법을 알아봅니다.
ms.date: 03/13/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 32047efcde093a3752bdd59baa88896d1547b93e
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546752"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a>Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark 설치

이 문서에서는 Azure HDInsight Spark 클러스터의 Jupyter Notebook에 .NET for Apache Spark를 설치하는 방법을 설명합니다. 명령줄과 Azure Portal을 조합하여 Azure HDInsight 클러스터에 .NET for Apache Spark를 배포할 수 있습니다(자세한 내용은 [Azure HDInsight에 .NET for Apache Spark 애플리케이션을 배포하는 방법](../tutorials/hdinsight-deployment.md) 참조). 하지만 Notebook은 보다 대화형이고 반복적인 환경을 제공합니다.

Azure HDInsight 클러스터에는Jupyter Notebook이 이미 제공되어 있으므로 Jupyter Notebook이 .NET for Apache Spark를 실행하도록 구성하기만 하면 됩니다. Jupyter Notebook에서 .NET for Apache Spark를 사용하려면 C# 코드를 한 줄씩 실행하고 필요한 경우 실행 상태를 유지하기 위해 C# REPL이 필요합니다. [Try .NET](https://github.com/dotnet/try)이 공식 .NET REPL으로 통합되었습니다.

Jupyter Notebook 환경을 통해 .NET for Apache Spark를 사용하도록 설정하려면 [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari)를 통해 몇 가지 수동 단계를 수행하고 HDInsight Spark 클러스터에 [스크립트 동작](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)을 제출해야 합니다.

> [!NOTE]
> 이 기능은 *실험적*이며 HDInsight Spark 팀에서 지원을 제공하지 않습니다.

## <a name="prerequisites"></a>사전 요구 사항

아직 없는 경우 [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-hdinsight-spark-cluster) 클러스터를 만듭니다.

1. [Azure Portal](https://portal.azure.com)에서 **+ 리소스 만들기**를 선택합니다.

1. 새 Azure HDInsight 클러스터 리소스를 만듭니다. 클러스터를 만드는 동안 **Spark 2.4** 및 **HDI 4.0**을 선택합니다.

## <a name="install-net-for-apache-spark"></a>.NET for Apache Spark 설치

Azure Portal에서 이전 단계에서 만든 **HDInsight Spark 클러스터**를 선택합니다.

### <a name="stop-the-livy-server"></a>Livy 서버 중지

1. 포털에서 **개요**를 선택하고 **Ambari 홈**을 선택합니다. 메시지가 표시되면 클러스터에 대한 로그인 자격 증명을 입력합니다.

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-ambari.png)

2. 왼쪽 탐색 메뉴에서 **Spark2**를 선택하고 **LIVY FOR SPARK2 SERVER**를 선택합니다.

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-livyserver.png)

3. **hn0... host**를 선택합니다.

   ![Livy 서버 중지](./media/hdinsight-notebook-installation/select-host.png)

4. **Livy for Spark2 Server** 옆에 있는 줄임표를 선택하고 **중지**를 선택합니다. 메시지가 표시되면 **확인**을 선택하여 계속합니다.

   Livy for Spark2 Server를 중지합니다.
   ![Livy 서버 중지](./media/hdinsight-notebook-installation/stop-server.png)

5. **hn1... host**에 대해서도 위 단계를 반복합니다.

### <a name="submit-an-hdinsight-script-action"></a>HDInsight 스크립트 동작 제출

1. `install-interactive-notebook.sh`는 .NET for Apache Spark를 설치하고 Apache Livy 및 sparkmagic을 변경하는 스크립트입니다. HDInsight에 스크립트 동작을 제출하기 전에 `install-interactive-notebook.sh`를 만들어 업로드해야 합니다.

   로컬 컴퓨터에 **install-interactive-notebook.sh**라는 새 파일을 만들고[install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh)의 내용을 붙여넣습니다.

   이 스크립트를 HDInsight 클러스터에서 액세스할 수 있는 [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions)에 업로드합니다. 예: `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.

2. [HDInsight 스크립트 동작](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)을 사용하여 클러스터에서 `install-interactive-notebook.sh`를 실행합니다.

   Azure Portal에서 HDI 클러스터로 돌아가서 왼쪽에 있는 옵션에서 **스크립트 동작**을 선택합니다. HDInsight Spark 클러스터에서 .NET for Apache Spark REPL을 배포하는 스크립트 동작 하나를 제출합니다. 다음 설정을 사용합니다.

   |속성  |설명  |
   |---------|---------|
   | 스크립트 유형 | 사용자 지정 |
   | 이름 | *.NET for Apache Spark 대화형 Notebook 환경 설치* |
   | Bash 스크립트 URI | `install-interactive-notebook.sh`를 업로드한 URI입니다. |
   | 노드 유형| 헤드 및 작업자 |
   | 매개 변수 | .NET for Apache Spark 버전. [.NET for Apache Spark 릴리스](https://github.com/dotnet/spark/releases)를 선택할 수 있습니다. 예를 들어 Sparkdotnet 버전 0.6.0을 설치하려는 경우 `0.6.0`입니다.

   스크립트 동작의 상태 옆에 녹색 확인 표시가 나타나면 다음 단계로 이동합니다.

### <a name="start-the-livy-server"></a>Livy 서버 시작

[Livy 서버 중단](#stop-the-livy-server) 섹션에 설명된 지침에 따라 호스트 **hn0** 및 **hn1**에 대해 Livy for Spark2 Server를 **시작**합니다(**중단**이 아님).

### <a name="set-up-spark-default-configurations"></a>Spark 기본 구성 설정

1. 포털에서 **개요**를 선택하고 **Ambari 홈**을 선택합니다. 메시지가 표시되면 클러스터에 대한 클러스터 로그인 자격 증명을 입력합니다.

2. **Spark2**, **CONFIGS**를 선택합니다. 그런 다음 **Custom spark2-defaults**를 선택합니다.

   ![구성 설정](./media/hdinsight-notebook-installation/spark-configs.png)

3. **속성 추가...** 를 선택하여 Spark 기본 설정을 추가합니다.

   ![속성 추가](./media/hdinsight-notebook-installation/add-property.png)

   세 가지 개별 속성이 있습니다. 단일 속성 추가 모드에서 **텍스트** 속성 형식을 사용하여 한 번에 하나씩 추가합니다. 키/값의 앞뒤에 추가 공백이 없는지 확인합니다.

   * **속성 1**
       * 키: &ensp;&ensp;`spark.dotnet.shell.command`
       * 값: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`

   * **속성 2** 이전 스크립트 동작에 포함된 .NET for Apache Spark 버전을 사용합니다.
       * 키: &ensp;&ensp;`spark.dotnet.packages`
       * 값: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`

   * **속성 3**
       * 키: &ensp;&ensp;`spark.dotnet.interpreter`
       * 값: `try`

   예를 들어 다음 이미지는 속성 1을 추가하는 설정입니다.

   ![구성 설정](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   세 개의 속성을 추가한 후 **저장**을 선택합니다. 구성 권장 사항의 경고 화면이 표시되면 **계속 진행**을 선택합니다.

4. 영향을 받는 구성 요소를 다시 시작합니다.

   새 속성을 추가한 후 변경 내용의 영향을 받는 구성 요소를 다시 시작해야 합니다. 맨 위에 있는 **다시 시작**을 선택하고, 드롭다운에서 **영향을 받는 모든 항목을 다시 시작**합니다.

   ![구성 설정](./media/hdinsight-notebook-installation/restart-affected.png)

   메시지가 표시되면 **모두 다시 시작 확인**을 선택하고 계속 진행하고 **확인**을 클릭하여 완료합니다.

## <a name="submit-jobs-through-a-jupyter-notebook"></a>Jupyter Notebook을 통해 작업 제출

이전 단계를 완료한 후 Jupyter Notebook을 통해 .NET for Apache Spark 작업을 제출할 수 있습니다.

1. 새 .NET for Apache Spark Notebook을 만듭니다. Azure Portal의 HDI 클러스터에서 Jupyter Notebook을 시작합니다.

   ![Jupyter Notebook 시작](./media/hdinsight-notebook-installation/launch-notebook.png)

   그런 다음 **새로 만들기** >  **.NET Spark(C#)** 를 선택하여 Notebook을 만듭니다.

   ![Jupyter 노트북](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. .NET for Apache Spark를 사용하여 작업을 제출합니다.

   다음 코드 조각을 사용하여 데이터 프레임을 만듭니다.

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Spark 작업 제출](./media/hdinsight-notebook-installation/create-df.png)

   다음 코드 조각을 사용하여 UDF(사용자 정의 함수)를 등록하고 데이터 프레임에 UDF를 사용합니다.

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Spark 작업 제출](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a>다음 단계

* [Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포](../tutorials/hdinsight-deployment.md)
* [HDInsight 설명서](https://docs.microsoft.com/azure/hdinsight/)
