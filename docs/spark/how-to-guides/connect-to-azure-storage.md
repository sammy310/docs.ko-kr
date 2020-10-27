---
title: 로컬 머신에서 원격 스토리지에 연결
description: 로컬 머신에서 .NET for Apache Spark를 사용하여 Azure Storage 계정에 연결합니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dc0c3b44279756596f3d456616821e690710ae04
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224016"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a>Azure Data Lake Storage Gen 2 또는 WASB 계정에 연결

이 문서에서는 Windows 머신에서 로컬로 실행되는 [.NET for Apache Spark](https://github.com/dotnet/spark) 인스턴스를 통해 ADLS(Azure Data Lake Storage) Gen 2 또는 WASB(Windows Azure Storage Blob) 계정에 연결하는 방법을 알아봅니다.

## <a name="set-up-the-environment"></a>환경 설정

1. [공식 웹 사이트](https://archive.apache.org/dist/spark/)에서 Hadoop 없이 빌드된 Apache Spark 배포를 다운로드하여([.NET for Apache Spark에서 지원](https://github.com/dotnet/spark#supported-apache-spark)되는 버전 선택) 디렉터리에 추출합니다. `SPARK_HOME` 환경 변수를 이 디렉터리로 설정합니다.
2. [여기](http://hadoop.apache.org/releases.html)에서 Apache Hadoop 이진 파일을 다운로드하여 폴더에 추출한 다음, `HADOOP_HOME` 환경 변수를 이 폴더로 설정합니다.
3. [이 위치](https://github.com/cdarlint/winutils)(이전 단계에서 설치한 Hadoop 버전에 따라 다름)에서 `winutils.exe` 및 `hadoop.dll` 파일을 다운로드하여 Hadoop의 bin 폴더에 저장합니다. 이진 파일은 Windows에서 모든 항목을 올바르게 설정하는 데 필요합니다(이 내용은 [관련 Apache 위키](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)에서 자세히 설명함).
4. `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` 파일을 다음과 같이 변경하여 Hadoop 설치를 구성합니다.
    1. Hadoop은 `JAVA_HOME`에 공백을 사용하지 않으므로 DOS 경로를 사용하여 `JAVA_HOME` 속성을 설정합니다. 다음과 같이 표시되어야 합니다. `C:\Progra~1\Java\jdk1.8.0_241`(로컬 머신에 설치한 Java 버전을 가리킴)
    2. `HADOOP_CLASSPATH`에 `%HADOOP_HOME%\share\hadoop\tools\lib\*`를 추가합니다.
    최종 `hadoop-env.cmd` 파일은 다음과 같습니다.

    ![최종 hadoop-env.cmd 파일](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a>Hadoop에서 스토리지 계정 구성

1. [Azure Portal](https://portal.azure.com)을 통해 연결하려는 ADLS Gen 2 또는 WASB 스토리지 계정을 열고 **설정** 블레이드에서 **액세스 키** 패널을 연 다음, key1에서 **키** 값을 복사합니다.
2. 이제 ADLS Gen2 계정에 액세스하도록 Hadoop을 구성하기 위해 클러스터 전체 구성이 포함된 `core-site.xml`(`%HADOOP_HOME%\etc\hadoop\`에 있음) 파일을 편집해야 합니다. 이 파일의 `<configuration>` 태그 안에 다음 속성을 추가합니다.

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    WASB 계정에 연결하려는 경우 속성 이름에서 `dfs`를 `blob`으로 바꿉니다. 예들 들어 `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`입니다.
3. `%HADOOP_HOME%` 디렉터리의 다음 명령을 실행하여 Hadoop에서 스토리지 계정 연결을 테스트할 수 있습니다.

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

URI를 통해 제공되는 경로의 모든 파일/폴더 목록이 표시됩니다.

> [!NOTE]
> 스토리지 계정의 URI를 얻는 형식은 다음과 같습니다.
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a>스토리지 계정에 연결

1. 위의 명령이 제대로 실행된 경우 이제 Spark를 통해 스토리지 계정에 액세스할 수 있습니다. 먼저 `%HADOOP_HOME%` 내에서 명령줄을 통해 `hadoop classpath` 명령을 실행하고 출력을 복사합니다.
2. 1단계에서 실행한 명령의 출력을 `SPARK_DIST_CLASSPATH` 환경 변수의 값으로 설정합니다.
3. 이제, 아래의 간단한 예제와 같이 abfs URI를 사용하여 Spark .NET을 통해 ADLS 또는 WASB 스토리지 계정에 액세스할 수 있습니다. (이 예제에서는 모든 Apache Spark 설치에 제공되는 표준 [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) 예제 파일을 사용합니다.)

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    표시되는 결과는 아래와 같은 DataFrame(`df`)입니다.

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
