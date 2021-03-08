---
title: .NET for Apache Spark 시작
description: Windows, macOS, Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 44859d1c4819853c07454429e8a83f1fbb2e3af5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103662"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>자습서: .NET for Apache Spark 시작

이 자습서에서는 Windows, macOS, Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * .NET for Apache Spark를 위한 환경 준비
> * 첫 번째 .NET for Apache Spark 애플리케이션 작성
> * .NET for Apache Spark 애플리케이션 빌드 및 실행

## <a name="prepare-your-environment"></a>환경 준비

앱 작성을 시작하기 전에 몇 가지 필수 구성 요소 종속성을 설치해야 합니다. 명령줄 환경에서 `dotnet`, `java`, `spark-shell`을 실행할 수 있는 경우 환경은 이미 준비된 것이며 다음 섹션으로 건너뛸 수 있습니다. 임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.

### <a name="1-install-net"></a>1. .NET 설치

.NET 앱 빌드를 시작하려면 .NET SDK(소프트웨어 개발 키트)를 다운로드하여 설치해야 합니다.

[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet/3.1)를 다운로드하여 설치합니다. SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.

.NET Core SDK를 설치한 후에는 새 명령 프롬프트 또는 터미널을 열고 `dotnet`을 실행합니다.

명령이 실행되고 dotnet 사용 방법에 대한 정보가 출력되면 다음 단계로 이동할 수 있습니다. `'dotnet' is not recognized as an internal or external command` 오류가 표시되면 명령을 실행하기 전에 **새** 명령 프롬프트 또는 터미널을 열어야 합니다.

### <a name="2-install-java"></a>2. Java 설치

Windows 및 macOS용 [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) 또는 Ubuntu용 [OpenJDK 8](https://openjdk.java.net/install/)을 설치합니다.

운영 체제에 적합한 버전을 선택합니다. 예를 들어 Windows x64 머신의 경우 **jdk-8u201-windows-x64.exe**(아래 참조), macOS의 경우 **jdk-8u231-macosx-x64.dmg** 를 선택합니다. 그런 다음, `java` 명령을 사용하여 설치를 확인합니다.

![Java 다운로드](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. 압축 소프트웨어 설치

Apache Spark는 압축된 .tgz 파일로 다운로드됩니다. [7-Zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 압축 풀기 프로그램을 사용하여 파일 압축을 풉니다.

### <a name="4-install-apache-spark"></a>4. Apache Spark 설치

[Apache Spark를 다운로드하여 설치](https://spark.apache.org/downloads.html)합니다. 버전 2.3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 또는 3.0.1 중에서 선택해야 합니다(.NET for Apache Spark는 다른 버전의 Apache Spark와 호환되지 않음).

다음 단계에서 사용되는 명령에서는 [Apache Spark 3.0.1을 다운로드하여 설치](https://spark.apache.org/downloads.html)했다고 가정합니다. 다른 버전을 사용하려는 경우 **3.0.1** 을 적절한 버전 번호로 바꿉니다. 그런 다음, **.tar** 파일 및 Apache Spark 파일의 압축을 풉니다.

중첩된 **.tar** 파일의 압축을 풀려면:

* 다운로드한 **spark-3.0.1-bin-hadoop2.7.tgz** 파일을 찾습니다.
* 파일을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 여기에 압축 풀기** 를 선택합니다.
* **spark-3.0.1-bin-hadoop2.7.tar** 이 다운로드한 **.tgz** 파일과 함께 생성됩니다.

Apache Spark 파일의 압축을 풀려면:

* **spark-3.0.1-bin-hadoop2.7.tar** 을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 압축 풀기...** 을 선택합니다.
* **압축 풀기** 필드에 **C:\bin** 을 입력합니다.
* **압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.
* **확인** 을 선택합니다.
* Apache Spark 파일이 C:\bin\spark-3.0.1-bin-hadoop2.7\에 추출됩니다.

![Spark 설치](./media/spark-extract-with-7-zip.png)

다음 명령을 실행하여 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다. Windows에서는 관리자 모드에서 명령 프롬프트를 실행해야 합니다.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin" # Warning: Don't run this if your path is already long as it will truncate your path to 1024 characters and potentially remove entries!
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

모든 항목을 설치하고 환경 변수를 설정한 후 **새** 명령 프롬프트 또는 터미널을 열고 다음 명령을 실행합니다.

```text
spark-submit --version
```

명령이 실행되고 버전 정보가 출력되면 다음 단계로 이동할 수 있습니다.

`'spark-submit' is not recognized as an internal or external command` 오류가 표시되면 **새** 명령 프롬프트를 열었는지 확인합니다.

### <a name="5-install-net-for-apache-spark"></a>5. .NET for Apache Spark 설치

.NET for Apache Spark GitHub에서 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다. 예를 들어 Windows 머신에서 .NET Core를 사용하려는 경우 [Windows x64 netcoreapp3.1 릴리스를 다운로드](https://github.com/dotnet/spark/releases)합니다.

Microsoft.Spark.Worker 압축을 풀려면:

* 다운로드한 **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** 파일을 찾습니다.
* 마우스 오른쪽 단추를 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.
* **압축 풀기** 필드에 **C:\bin** 을 입력합니다.
* **압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.
* **확인** 을 선택합니다.

### <a name="6-install-winutils-windows-only"></a>6. WinUtils 설치(Windows에만 해당)

.NET for Apache Spark를 사용하려면 Apache Spark와 함께 WinUtils를 설치해야 합니다. [winutils.exe를 다운로드](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)합니다. 그런 다음, WinUtils를 **C:\bin\spark-3.0.1-bin-hadoop2.7\bin** 에 복사합니다.

> [!NOTE]
> 다른 Hadoop 버전을 사용 중인 경우(Spark 설치 폴더 이름 끝에 주석으로 처리되어 있음) 해당 Hadoop 버전과 호환되는 [WinUtils 버전을 선택](https://github.com/steveloughran/winutils)합니다.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. DOTNET_WORKER_DIR 설정 및 종속성 확인

다음 명령 중 하나를 실행하여 .NET 앱에서 .NET for Apache Spark 작업자 바이너리를 찾는 데 사용하는 `DOTNET_WORKER_DIR` 환경 변수를 설정합니다. `<PATH-DOTNET_WORKER_DIR>`을 `Microsoft.Spark.Worker`를 다운로드하여 압축을 푼 디렉터리로 바꿉니다. Windows에서는 관리자 모드에서 명령 프롬프트를 실행해야 합니다.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

마지막으로, 다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.

## <a name="write-a-net-for-apache-spark-app"></a>.NET for Apache Spark 앱 작성

### <a name="1-create-a-console-app"></a>1. 콘솔 앱 만들기

명령 프롬프트 또는 터미널에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다. `-o` 매개 변수는 앱이 저장되는 *MySparkApp* 이라는 디렉터리를 만들고 필요한 파일로 채웁니다. `cd MySparkApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.

### <a name="2-install-nuget-package"></a>2. NuGet 패키지 설치

앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다. 명령 프롬프트 또는 터미널에서 다음 명령을 실행합니다.

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> 달리 지정하지 않은 한 이 자습서에서는 `Microsoft.Spark` NuGet 패키지의 최신 버전을 사용합니다.

### <a name="3-write-your-app"></a>3. 앱 작성

Visual Studio Code 또는 텍스트 편집기에서 *Program.cs* 를 열고 모든 코드를 다음으로 바꿉니다.

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

[SparkSession](xref:Microsoft.Spark.Sql.SparkSession)은 Apache Spark 애플리케이션의 진입점으로, 애플리케이션의 컨텍스트 및 정보를 관리합니다. [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) 메서드를 사용하여 `filePath`에서 지정된 파일의 텍스트 데이터를 [DataFrame](xref:Microsoft.Spark.Sql.DataFrame)으로 읽어옵니다. DataFrame은 명명된 열의 집합으로 데이터를 구성하는 방법입니다. 그런 다음 일련의 변환을 적용하여 파일의 문장을 분할하고, 각 단어를 그룹화하고, 개수를 계산하고, 내림차순으로 정렬합니다. 이러한 작업의 결과는 다른 DataFrame에 저장됩니다. 이 시점에서는 아무 작업도 수행되지 않습니다. .NET for Apache Spark가 데이터를 지연 계산하기 때문입니다. [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) 메서드를 호출하여 콘솔에 `words`로 변환된 DataFrame의 내용을 표시하기 전에는 위의 줄에 정의된 작업이 실행되지 않습니다. Spark 세션이 더 이상 필요하지 않으면 [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) 메서드를 사용하여 세션을 중지합니다.

### <a name="4-create-data-file"></a>4. 데이터 파일 만들기

앱은 텍스트 줄이 포함된 파일을 처리합니다. *MySparkApp* 디렉터리에 다음 텍스트를 포함하는 *input.txt* 라는 파일을 만듭니다.

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

변경 내용을 저장하고 파일을 닫습니다.

## <a name="run-your-net-for-apache-spark-app"></a>.NET for Apache Spark 앱 실행

다음 명령을 실행하여 애플리케이션을 빌드합니다.

```dotnetcli
dotnet build
```

빌드 출력 디렉터리로 이동하고 `spark-submit` 명령을 사용하여 Apache Spark에서 실행할 애플리케이션을 제출합니다. `<version>`을 .NET 작업자의 버전으로 바꾸고 `<path-of-input.txt>`를 *input.txt* 파일이 저장된 경로로 바꿔야 합니다.

### <a name="windows"></a>[Windows](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> 이 명령은 Apache Spark를 다운로드한 후 PATH 환경 변수에 추가했으므로 `spark-submit`를 사용할 수 있다고 전제합니다. 그렇지 않은 경우에는 전체 경로를 사용해야 합니다(예: *C:\bin\apache-spark\bin\spark-submit* 또는 *~/spark/bin/spark-submit*).

앱이 실행되면 *input.txt* 파일의 단어 수 데이터가 콘솔에 기록됩니다.

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

지금까지 .NET for Apache Spark 앱을 작성하고 실행했습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업 방법을 알아보았습니다.
> [!div class="checklist"]
>
> * .NET for Apache Spark를 위한 환경 준비
> * 첫 번째 .NET for Apache Spark 애플리케이션 작성
> * .NET for Apache Spark 애플리케이션 빌드 및 실행

위의 단계를 설명하는 동영상을 보려면 [.NET for Apache Spark 101 동영상 시리즈](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)를 확인하세요.

자세한 내용은 리소스 페이지를 참조하세요.
> [!div class="nextstepaction"]
> [.NET for Apache Spark 리소스](../resources/index.md)
