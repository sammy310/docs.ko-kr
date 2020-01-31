---
title: .NET for Apache Spark 시작
description: Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 679ee7660e96504768a781e1e384acab80362736
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743207"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>자습서: .NET for Apache Spark 시작

이 자습서에서는 Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * .NET for Apache Spark를 위한 Windows 환경 준비
> * 첫 번째 .NET for Apache Spark 애플리케이션 작성
> * 간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행

## <a name="prepare-your-environment"></a>환경 준비

앱 작성을 시작하기 전에 몇 가지 필수 구성 요소 종속성을 설치해야 합니다. 명령줄 환경에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는 경우 환경은 이미 준비된 것이며 다음 섹션으로 건너뛸 수 있습니다. 임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.

### <a name="1-install-net"></a>1. .NET 설치

.NET 앱 빌드를 시작하려면 .NET SDK(소프트웨어 개발 키트)를 다운로드하여 설치해야 합니다.

[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0)를 다운로드하여 설치합니다. SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.

.NET Core SDK를 설치한 후에는 새 명령 프롬프트를 열고 `dotnet`을 실행합니다.

명령이 실행되고 dotnet 사용 방법에 대한 정보가 출력되면 다음 단계로 이동할 수 있습니다. `'dotnet' is not recognized as an internal or external command` 오류가 표시되면 명령을 실행하기 전에 **새** 명령 프롬프트를 열어야 합니다.

### <a name="2-install-java"></a>2. Java 설치

[Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)을 설치합니다.

운영 체제에 적합한 버전을 선택합니다. 예를 들어 Windows x64 머신의 경우 **jdk-8u201-windows-x64.exe**를 선택합니다. 그런 다음, `java` 명령을 사용하여 설치를 확인합니다.

![Java 다운로드](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a>3. 7-zip 설치

Apache Spark는 압축된 .tgz 파일로 다운로드됩니다. 7-zip 같은 압축 풀기 프로그램을 사용하여 파일 압축을 풉니다.

* [7-Zip 다운로드](https://www.7-zip.org/)를 방문합니다.
* 페이지의 첫 번째 표에서 운영 체제에 따라 32비트 x86 또는 64비트 x64 다운로드를 선택합니다.
* 다운로드가 완료되면 설치 관리자를 실행합니다.

![7Zip 다운로드](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a>4. Apache Spark 설치

[Apache Spark를 다운로드하여 설치](https://spark.apache.org/downloads.html)합니다. 버전 2.3.* 또는 2.4.0, 2.4.1, 2.4.3, 2.4.4 중에서 선택해야 합니다(.NET for Apache Spark는 다른 버전의 Apache Spark와 호환되지 않음).

다음 단계에서 사용되는 명령에서는 [Apache Spark 2.4.1을 다운로드하여 설치](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)했다고 가정합니다. 다른 버전을 사용하려는 경우 **2.4.1**을 적절한 버전 번호로 바꿉니다. 그런 다음, **.tar** 파일 및 Apache Spark 파일의 압축을 풉니다.

중첩된 **.tar** 파일의 압축을 풀려면:

* 다운로드한 **spark-2.4.1-bin-hadoop2.7.tgz** 파일을 찾습니다.
* 파일을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 여기에 압축 풀기**를 선택합니다.
* **spark-2.4.1-bin-hadoop2.7.tar**이 다운로드한 **.tgz** 파일과 함께 생성됩니다.

Apache Spark 파일의 압축을 풀려면:

* **spark-2.4.1-bin-hadoop2.7.tar**을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.
* **압축 풀기** 필드에 **C:\bin**을 입력합니다.
* **압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.
* **확인**을 선택합니다.
* Apache Spark 파일이 C:\bin\spark-2.4.1-bin-hadoop2.7\에 추출되었습니다.

![Spark 설치](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

다음 명령을 실행하여 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다.

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

모든 항목을 설치하고 환경 변수를 설정한 후 **새** 명령 프롬프트를 열고 다음 명령을 실행합니다.

`%SPARK_HOME%\bin\spark-submit --version`

명령이 실행되고 버전 정보가 출력되면 다음 단계로 이동할 수 있습니다.

`'spark-submit' is not recognized as an internal or external command` 오류가 표시되면 **새** 명령 프롬프트를 열었는지 확인합니다.

### <a name="5-install-net-for-apache-spark"></a>5. .NET for Apache Spark 설치

.NET for Apache Spark GitHub에서 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다. 예를 들어 Windows 머신에서 .NET Core를 사용하려는 경우 [Windows x64 netcoreapp2.1 릴리스를 다운로드](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip)합니다.

Microsoft.Spark.Worker 압축을 풀려면:

* 다운로드한 **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** 파일을 찾습니다.
* 마우스 오른쪽 단추를 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.
* **압축 풀기** 필드에 **C:\bin**을 입력합니다.
* **압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.
* **확인**을 선택합니다.

![.NET Spark 설치](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a>6. WinUtils 설치

.NET for Apache Spark를 사용하려면 Apache Spark와 함께 WinUtils를 설치해야 합니다. [winutils.exe를 다운로드](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)합니다. 그런 다음, WinUtils를 **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**에 복사합니다.

> [!NOTE]
> 다른 Hadoop 버전을 사용 중인 경우(Spark 설치 폴더 이름 끝에 주석으로 처리되어 있음) 해당 Hadoop 버전과 호환되는 [WinUtils 버전을 선택](https://github.com/steveloughran/winutils)합니다.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. DOTNET_WORKER_DIR 설정 및 종속성 확인

다음 명령을 실행하여 .NET 앱에서 .NET for Apache Spark를 찾는 데 사용하는 `DOTNET_WORKER_DIR` 환경 변수를 설정합니다.

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

마지막으로, 다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.

## <a name="write-a-net-for-apache-spark-app"></a>.NET for Apache Spark 앱 작성

### <a name="1-create-a-console-app"></a>1. 콘솔 앱 만들기

명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다. `-o` 매개 변수는 앱이 저장되는 *mySparkApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다. `cd mySparkApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.

### <a name="2-install-nuget-package"></a>2. NuGet 패키지 설치

앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다. 명령 프롬프트에서 다음 명령을 실행합니다.

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a>3. 앱 코딩

Visual Studio Code 또는 텍스트 편집기에서 *Program.cs*를 열고 모든 코드를 다음으로 바꿉니다.

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a>4. 데이터 파일 추가

앱은 텍스트 줄이 포함된 파일을 처리합니다. *mySparkApp* 디렉터리에 다음 텍스트를 포함하는 *input.txt* 파일을 만듭니다.

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a>.NET for Apache Spark 앱 실행

1. 다음 명령을 실행하여 애플리케이션을 빌드합니다.

   ```dotnetcli
   dotnet build
   ```

2. 다음 명령을 실행하여 Apache Spark에서 실행할 애플리케이션을 제출합니다.

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. 앱이 실행되면 *input.txt* 파일의 단어 수 데이터가 콘솔에 기록됩니다.

지금까지 .NET for Apache Spark 앱을 작성하고 실행했습니다.

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
>
> * .NET for Apache Spark를 위한 Windows 환경 준비
> * 첫 번째 .NET for Apache Spark 애플리케이션 작성
> * 간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행

위의 단계를 설명하는 동영상을 보려면 [.NET for Apache Spark 101 동영상 시리즈](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)를 확인하세요.

자세한 내용은 리소스 페이지를 참조하세요.
> [!div class="nextstepaction"]
> [.NET for Apache Spark 리소스](../resources/index.md)
