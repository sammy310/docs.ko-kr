---
title: Apache Spark 용 .NET 시작
description: Windows에서 .NET Core를 사용 하 여 Apache Spark 앱 용 .NET을 실행 하는 방법을 알아봅니다.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577010"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>자습서: Apache Spark 용 .NET 시작

이 자습서에서는 Windows에서 .NET Core를 사용 하 여 Apache Spark 앱 용 .NET을 실행 하는 방법을 배웁니다.

이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
> * Apache Spark 용 .NET 용 Windows 환경 준비
> * **Microsoft Spark Worker** 를 다운로드 합니다.
> * Apache Spark 응용 프로그램에 대 한 간단한 .NET 빌드 및 실행

## <a name="prepare-your-environment"></a>환경 준비

시작 하기 `dotnet`전에 명령줄 `spark-shell` 에서,,를 실행할 `java` `mvn`수 있는지 확인 합니다. 사용자 환경이 이미 준비 된 경우 다음 섹션으로 건너뛸 수 있습니다. 일부 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행 합니다.

1. [.Net Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 다운로드 하 여 설치 합니다. SDK를 설치 하면 도구 체인 `dotnet` 가 경로에 추가 됩니다. PowerShell 명령을 `dotnet --version` 사용 하 여 설치를 확인 합니다.

2. 최신 업데이트를 사용 하 여 [Visual studio 2017](https://www.visualstudio.com/downloads/) 또는 [visual studio 2019](https://visualstudio.microsoft.com/vs/preview/) 를 설치 합니다. Community, Professional 또는 Enterprise를 사용할 수 있습니다. 커뮤니티 버전은 무료입니다.

   설치 하는 동안 다음 작업을 선택 합니다.
      * .NET 데스크톱 개발
          * 모든 필수 구성 요소
          * .NET Framework 4.6.1 개발 도구
      * .NET Core 플랫폼 간 개발
          * 모든 필수 구성 요소

3. [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)을 설치 합니다.

    * 운영 체제에 적합 한 버전을 선택 합니다. 예를 들어 Windows x64 컴퓨터에 대해 **jdk-8u201-windows-x64** 를 선택 합니다.
    * PowerShell 명령을 `java -version` 사용 하 여 설치를 확인 합니다.

4. [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)를 설치 합니다.
    * [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)를 다운로드 합니다.
    * 로컬 디렉터리로 추출 합니다. `c:\bin\apache-maven-3.6.0\` )을 입력합니다.
    * [PATH 환경 변수에](https://www.java.com/en/download/help/path.xml)Apache Maven를 추가 합니다. 로 `c:\bin\apache-maven-3.6.0\`압축을 푼 경우 경로에를 `c:\bin\apache-maven-3.6.0\bin` 추가 합니다.
    * PowerShell 명령을 `mvn -version` 사용 하 여 설치를 확인 합니다.

5. [Apache Spark 2.3 이상](https://spark.apache.org/downloads.html)을 설치 합니다. Apache Spark 2.4 +는 지원 되지 않습니다.
    * [2.3 이상 Apache Spark](https://spark.apache.org/downloads.html) 를 다운로드 하 고 [7-zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 도구를 사용 하 여 로컬 폴더에 추출 합니다. 예를 들어로 `c:\bin\spark-2.3.2-bin-hadoop2.7\`추출할 수 있습니다.
    * [PATH 환경 변수에](https://www.java.com/en/download/help/path.xml)Apache Spark를 추가 합니다. 로 `c:\bin\spark-2.3.2-bin-hadoop2.7\`압축을 푼 경우 경로에를 `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` 추가 합니다.
    * 이라는`SPARK_HOME` [새 환경 변수](https://www.java.com/en/download/help/path.xml) 를 추가 합니다. 로 `C:\bin\spark-2.3.2-bin-hadoop2.7\`압축을 푼 경우 **변수 값**에을 사용 `C:\bin\spark-2.3.2-bin-hadoop2.7\` 합니다.
    * 명령줄에서를 실행할 `spark-shell` 수 있는지 확인 합니다.

6. [Winutils.exe](https://github.com/steveloughran/winutils)를 설정 합니다.
    * [Winutils.exe 리포지토리에서](https://github.com/steveloughran/winutils) **winutils.exe** binary를 다운로드 합니다. Spark 배포가 컴파일된 Hadoop의 버전을 선택 합니다. 예를 들어 **Spark 2.3.2**에 **hadoop-2.7.1** 를 사용 합니다. Hadoop 버전은 Spark 설치 폴더 이름의 끝에 주석이 추가 됩니다.
    * 원하는 디렉터리에 **winutils.exe** binary를 저장 합니다. `c:\hadoop\bin` )을 입력합니다.
    * 를 `HADOOP_HOME` 사용 하지 않고 `bin` **winutils.exe** 를 사용 하 여 디렉터리를 반영 하도록 설정 합니다. `c:\hadoop` )을 입력합니다.
    * PATH 환경 변수를 포함 `%HADOOP_HOME%\bin`하도록 설정 합니다.

다음 섹션으로 이동 하기 전에 `dotnet`명령줄 `java`에서 `mvn`, `spark-shell` ,를 실행할 수 있는지 확인 합니다.

## <a name="download-the-microsoftsparkworker-release"></a>Microsoft Spark Worker 릴리스를 다운로드 합니다.

1. Apache Spark GitHub 릴리스 페이지의 .NET에서 로컬 컴퓨터로 [Microsoft Spark Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드 합니다. 예를 들어, `c:\bin\Microsoft.Spark.Worker\`경로에 다운로드할 수 있습니다.

2. 이라는 `DotnetWorkerPath` [새 환경 변수](https://www.java.com/en/download/help/path.xml) 를 만들어이를 다운로드 하 고 압축을 푼 디렉터리로 설정 합니다. `c:\bin\Microsoft.Spark.Worker` )을 입력합니다.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Apache Spark GitHub 리포지토리의 .NET 복제

다음 [Gitbash](https://gitforwindows.org/) 명령을 사용 하 여 Apache Spark 리포지토리의 .net을 컴퓨터에 복제 합니다.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Apache Spark 앱에 대 한 .NET 작성

1. **Visual Studio** 를 열고 **파일 > 새 프로젝트 만들기 > 콘솔 앱 (.net Core)** 으로 이동 합니다. 응용 프로그램 이름을 **HelloSpark**로 합니다.

2. [Microsoft Spark NuGet 패키지](https://www.nuget.org/profiles/spark)를 설치 합니다. NuGet 패키지를 설치 하는 방법에 대 한 자세한 내용은 [Nuget 패키지를 설치 하는 다양 한 방법](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)을 참조 하세요.

3. **솔루션 탐색기**에서 **Program.cs** 을 열고 다음 C# 코드를 작성 합니다.

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. 솔루션을 빌드합니다.

## <a name="run-your-net-for-apache-spark-app"></a>Apache Spark 앱에 대 한 .NET 실행

1. **PowerShell** 을 열고 디렉터리를 앱이 저장 된 폴더로 변경 합니다.

   ```powershell
   cd <your-app-output-directory>
   ```

2. 다음 콘텐츠를 사용 하 여 **사용자: json** 이라는 파일을 만듭니다.

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. 다음 PowerShell 명령을 사용 하 여 앱을 실행 합니다.

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

축하합니다. Apache Spark 앱에 대 한 .NET을 작성 하 고 실행 했습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 다음 작업을 수행하는 방법을 알아보았습니다.
> [!div class="checklist"]
> * Apache Spark 용 .NET 용 Windows 환경 준비
> * **Microsoft Spark Worker** 를 다운로드 합니다.
> * Apache Spark 응용 프로그램에 대 한 간단한 .NET 빌드 및 실행

자세한 내용은 리소스 페이지를 확인 하세요.
> [!div class="nextstepaction"]
> [Apache Spark 리소스에 대 한 .NET](../resources/index.md)
