---
title: 로컬 머신에서 원격 스토리지에 연결
description: 로컬 머신에서 .NET for Apache Spark를 사용하여 Azure Storage 계정에 연결합니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 09e92b0cae848f9c98b691a11842f131f613396b
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878047"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a><span data-ttu-id="cf4a9-103">Azure Data Lake Storage Gen 2 또는 WASB 계정에 연결</span><span class="sxs-lookup"><span data-stu-id="cf4a9-103">Connect to Azure Data Lake Storage Gen 2 or WASB account</span></span>

<span data-ttu-id="cf4a9-104">이 문서에서는 Windows 머신에서 로컬로 실행되는 [.NET for Apache Spark](https://github.com/dotnet/spark) 인스턴스를 통해 ADLS(Azure Data Lake Storage) Gen 2 또는 WASB(Windows Azure Storage Blob) 계정에 연결하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-104">In this article, you learn how to connect to an Azure Data Lake Storage (ADLS) Gen 2 or Windows Azure Storage Blob (WASB) account through an instance of [.NET for Apache Spark](https://github.com/dotnet/spark) running locally on your Windows machine.</span></span>

## <a name="set-up-the-environment"></a><span data-ttu-id="cf4a9-105">환경 설정</span><span class="sxs-lookup"><span data-stu-id="cf4a9-105">Set up the environment</span></span>

1. <span data-ttu-id="cf4a9-106">[공식 웹 사이트](https://archive.apache.org/dist/spark/)에서 Hadoop 없이 빌드된 Apache Spark 배포를 다운로드하여([.NET for Apache Spark에서 지원](https://github.com/dotnet/spark#supported-apache-spark)되는 버전 선택) 디렉터리에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-106">Download the Apache Spark distribution built without Hadoop from [official website](https://archive.apache.org/dist/spark/) (choose a version [supported by .NET for Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)), and extract it to a directory.</span></span> <span data-ttu-id="cf4a9-107">`SPARK_HOME` 환경 변수를 이 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-107">Set the environment variable `SPARK_HOME` to this directory.</span></span>
2. <span data-ttu-id="cf4a9-108">[여기](http://hadoop.apache.org/releases.html)에서 Apache Hadoop 이진 파일을 다운로드하여 폴더에 추출한 다음, `HADOOP_HOME` 환경 변수를 이 폴더로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-108">Download the Apache Hadoop binary from [here](http://hadoop.apache.org/releases.html) and extract to a folder, and set your `HADOOP_HOME` environment variable to this folder.</span></span>
3. <span data-ttu-id="cf4a9-109">[이 위치](https://github.com/cdarlint/winutils)(이전 단계에서 설치한 Hadoop 버전에 따라 다름)에서 `winutils.exe` 및 `hadoop.dll` 파일을 다운로드하여 Hadoop의 bin 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-109">Download the `winutils.exe` and `hadoop.dll` files from [this location](https://github.com/cdarlint/winutils) (depending on the version of Hadoop installed in the previous step) and put them in the bin folder of your Hadoop.</span></span> <span data-ttu-id="cf4a9-110">이진 파일은 Windows에서 모든 항목을 올바르게 설정하는 데 필요합니다(이 내용은 [관련 Apache 위키](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)에서 자세히 설명함).</span><span class="sxs-lookup"><span data-stu-id="cf4a9-110">These binaries are needed on Windows in order to get everything setup correctly (this is explained in detail in the [Apache wiki here](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span></span>
4. <span data-ttu-id="cf4a9-111">`%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` 파일을 다음과 같이 변경하여 Hadoop 설치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-111">Configure your Hadoop installation by making the following changes to your `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` file:</span></span>
    1. <span data-ttu-id="cf4a9-112">Hadoop은 `JAVA_HOME`에 공백을 사용하지 않으므로 DOS 경로를 사용하여 `JAVA_HOME` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-112">Set the `JAVA_HOME` property using the DOS path (since Hadoop doesn't like spaces in `JAVA_HOME`).</span></span> <span data-ttu-id="cf4a9-113">다음과 같이 표시되어야 합니다. `C:\Progra~1\Java\jdk1.8.0_241`(로컬 머신에 설치한 Java 버전을 가리킴)</span><span class="sxs-lookup"><span data-stu-id="cf4a9-113">This should look something like this: `C:\Progra~1\Java\jdk1.8.0_241` (Pointing to whatever version of Java you have installed on your local machine).</span></span>
    2. <span data-ttu-id="cf4a9-114">`HADOOP_CLASSPATH`에 `%HADOOP_HOME%\share\hadoop\tools\lib\*`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-114">Append `%HADOOP_HOME%\share\hadoop\tools\lib\*` to `HADOOP_CLASSPATH`.</span></span>
    <span data-ttu-id="cf4a9-115">최종 `hadoop-env.cmd` 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-115">Your final `hadoop-env.cmd` file should look something like this:</span></span>

    ![최종 hadoop-env.cmd 파일](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a><span data-ttu-id="cf4a9-117">Hadoop에서 스토리지 계정 구성</span><span class="sxs-lookup"><span data-stu-id="cf4a9-117">Configure your storage account in Hadoop</span></span>

1. <span data-ttu-id="cf4a9-118">[Azure Portal](https://portal.azure.com)을 통해 연결하려는 ADLS Gen 2 또는 WASB 스토리지 계정을 열고 **설정** 블레이드에서 **액세스 키** 패널을 연 다음, key1에서 **키** 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-118">Open the ADLS Gen 2 or WASB storage account you want to connect to through the [Azure portal](https://portal.azure.com) and open the **Access keys** panel under the **Settings** blade and copy the value of **Key** from under key1.</span></span>
2. <span data-ttu-id="cf4a9-119">이제 ADLS Gen2 계정에 액세스하도록 Hadoop을 구성하기 위해 클러스터 전체 구성이 포함된 `core-site.xml`(`%HADOOP_HOME%\etc\hadoop\`에 있음) 파일을 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-119">Now in order to configure Hadoop to access your ADLS Gen2 account you would have to edit your `core-site.xml` (located in `%HADOOP_HOME%\etc\hadoop\` ) file which contains cluster-wide configuration.</span></span> <span data-ttu-id="cf4a9-120">이 파일의 `<configuration>` 태그 안에 다음 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-120">Add the following properties inside the `<configuration>` tags in this file:</span></span>

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

    <span data-ttu-id="cf4a9-121">WASB 계정에 연결하려는 경우 속성 이름에서 `dfs`를 `blob`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-121">If you are trying to connect to a WASB account, replace `dfs` with `blob` in the property names.</span></span> <span data-ttu-id="cf4a9-122">예들 들어 `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-122">For example, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span></span>
3. <span data-ttu-id="cf4a9-123">`%HADOOP_HOME%` 디렉터리의 다음 명령을 실행하여 Hadoop에서 스토리지 계정 연결을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-123">You can test the connectivity to your Storage Account from Hadoop by running the following command from your `%HADOOP_HOME%` directory:</span></span>

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

<span data-ttu-id="cf4a9-124">URI를 통해 제공되는 경로의 모든 파일/폴더 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-124">This should display a list of all files/folders in the path provided by your URI.</span></span>

> [!NOTE]
> <span data-ttu-id="cf4a9-125">스토리지 계정의 URI를 얻는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-125">The format to derive the URI to your Storage account is as follows:</span></span>
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a><span data-ttu-id="cf4a9-126">스토리지 계정에 연결</span><span class="sxs-lookup"><span data-stu-id="cf4a9-126">Connect to your storage account</span></span>

1. <span data-ttu-id="cf4a9-127">위의 명령이 제대로 실행된 경우 이제 Spark를 통해 스토리지 계정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-127">If the above command worked, you can now move on to accessing this storage account through Spark.</span></span> <span data-ttu-id="cf4a9-128">먼저 `%HADOOP_HOME%` 내에서 명령줄을 통해 `hadoop classpath` 명령을 실행하고 출력을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-128">First run the command `hadoop classpath` from the commandline inside `%HADOOP_HOME%` and copy the output.</span></span>
2. <span data-ttu-id="cf4a9-129">1단계에서 실행한 명령의 출력을 `SPARK_DIST_CLASSPATH` 환경 변수의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-129">Set the output of the command run in Step 1 to the value of environment variable `SPARK_DIST_CLASSPATH`.</span></span>
3. <span data-ttu-id="cf4a9-130">이제, 아래의 간단한 예제와 같이 abfs URI를 사용하여 Spark .NET을 통해 ADLS 또는 WASB 스토리지 계정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-130">Now you should be able to access your ADLS or WASB storage account through Spark .NET using the abfs URI as shown in the simple example below.</span></span> <span data-ttu-id="cf4a9-131">(이 예제에서는 모든 Apache Spark 설치에 제공되는 표준 [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) 예제 파일을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="cf4a9-131">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.):</span></span>

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    <span data-ttu-id="cf4a9-132">표시되는 결과는 아래와 같은 DataFrame(`df`)입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-132">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
