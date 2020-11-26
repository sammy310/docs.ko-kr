---
title: Azure HDInsight에 Apache Spark 작업의 .NET 제출
description: Apache Livy 및 spark-submit을 사용하여 Azure HDInsight에 Apache Spark 작업의 .NET을 제출하는 방법에 대해 알아봅니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688165"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Azure HDInsight에 Apache Spark 작업의 .NET 제출

Apache Spark 작업의 .NET을 HDInsight에 배포하는 방법에는 두 가지 방법(`spark-submit` 및 Apache Livy)이 있습니다.

## <a name="deploy-using-spark-submit"></a>spark-submit을 사용하여 배포

[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 명령을 사용하여 Azure HDInsight에 .NET for Apache Spark 작업을 제출할 수 있습니다.

1. Azure Portal에서 해당 HDInsight Spark 클러스터로 이동한 다음, **SSH + 클러스터 로그인** 을 선택합니다.

2. ssh 로그인 정보를 복사하고 터미널에 로그인을 붙여넣습니다. 클러스터를 만드는 동안 설정한 암호를 사용하여 클러스터에 로그인합니다. Ubuntu 및 Spark에 오신 것을 환영하는 메시지가 표시됩니다.

3. **spark-submit** 명령을 사용하여 HDInsight 클러스터에서 앱을 실행합니다. 예제 스크립트의 **mycontainer** 및 **mystorageaccount** 를 Blob 컨테이너 및 스토리지 계정의 실제 이름으로 바꾸어야 합니다. 또한 사용되는 Spark 및 .NET for Apache Spark의 버전으로 microsoft-spark jar를 바꿔야 합니다.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Apache Livy를 사용하여 배포

Apache Spark REST API인 [Apache Livy](https://livy.incubator.apache.org/)를 사용하여 Azure HDInsight Spark 클러스터에 .NET for Apache Spark 작업을 제출할 수 있습니다. 자세한 내용은 [Apache Livy를 사용한 원격 작업](/azure/hdinsight/spark/apache-spark-livy-rest-interface)을 참조하세요.

`curl`을 사용하여 Linux에서 다음 명령을 실행할 수 있습니다.

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>다음 단계

* [.NET for Apache Spark 시작](../tutorials/get-started.md)
* [Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포](../tutorials/hdinsight-deployment.md)
* [HDInsight 설명서](/azure/hdinsight/)
