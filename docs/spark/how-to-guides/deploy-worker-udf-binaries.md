---
title: Apache Spark 작업자 및 사용자 정의 함수 이진 파일용 .NET 배포
description: Apache Spark 작업자 및 사용자 정의 함수 이진 파일용 .NET을 배포하는 방법에 대해 알아봅니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 001798bfda628ce979570bcd89e7c5553347b275
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91954960"
---
# <a name="deploy-net-for-apache-spark-worker-and-user-defined-function-binaries"></a>Apache Spark 작업자 및 사용자 정의 함수 이진 파일용 .NET 배포

이 방법은 Apache Spark 작업자 및 사용자 정의 함수 이진 파일용 .NET을 배포하는 방법에 대한 일반적인 지침을 제공합니다. `spark-submit`를 사용하여 애플리케이션을 시작하는 데 일반적으로 사용되는 매개 변수뿐만 아니라 설정할 환경 변수를 알아봅니다.

## <a name="configurations"></a>구성

구성에는 Apache Spark 작업자 및 사용자 정의 함수 이진 파일용 .NET을 배포하기 위해 일반적인 환경 변수 및 매개 변수 설정이 표시됩니다.

### <a name="environment-variables"></a>환경 변수

작업자를 배포하고 UDF를 작성하는 경우 다음과 같은 일반적으로 사용되는 몇 가지 환경 변수를 설정해야 할 수 있습니다.

| 환경 변수         | 설명
| :--------------------------- | :----------
| DOTNET_WORKER_DIR            | <code>Microsoft.Spark.Worker</code> 이진 파일이 생성된 경로입니다.</br>Spark 드라이버에서 사용되며 Spark 실행기에 전달됩니다. 이 변수가 설정되지 않은 경우 Spark 실행기는 <code>PATH</code> 환경 변수에 지정된 경로를 검색합니다.</br>_예: "C:\bin\Microsoft.Spark.Worker"_
| DOTNET_ASSEMBLY_SEARCH_PATHS | <code>Microsoft.Spark.Worker</code>에서 어셈블리를 로드할 쉼표로 구분된 경로입니다.</br>경로가 "."으로 시작하면 작업 디렉터리가 앞에 배치됩니다. **Yarn 모드**인 경우 "."은 컨테이너의 작업 디렉터리를 나타냅니다.</br>_예: "C:\Users\\&lt;사용자 이름&gt;\\&lt;mysparkapp&gt;\bin\Debug\\&lt;dotnet 버전&gt;"_
| DOTNET_WORKER_DEBUG          | <a href="https://github.com/dotnet/spark/blob/master/docs/developer-guide.md#debugging-user-defined-function-udf">UDF를 디버그</a>하려면 <code>spark-submit</code>를 실행하기 전에 이 환경 변수를 <code>1</code>로 설정합니다.

### <a name="parameter-options"></a>매개 변수 옵션
Spark 애플리케이션이 [번들로 제공](https://spark.apache.org/docs/latest/submitting-applications.html#bundling-your-applications-dependencies)되면 `spark-submit`을 사용하여 시작할 수 있습니다. 다음 표에서는 일반적으로 사용되는 일부 옵션을 보여 줍니다.

| 매개 변수 이름        | 설명
| :---------------------| :----------
| --class               | 애플리케이션의 진입점입니다.</br>_예: org.apache.spark.deploy.dotnet.DotnetRunner_
| --master              | 클러스터의 <a href="https://spark.apache.org/docs/latest/submitting-applications.html#master-urls">마스터 URL</a>입니다.</br>_예: Yarn_
| --deploy-mode         | 작업자 노드(<code>cluster</code>) 또는 외부 클라이언트(<code>client</code>)로 로컬 배포할지 여부입니다.</br>기본값: <code>client</code>
| --conf                | <code>key=value</code> 형식의 임의 Spark 구성 속성입니다.</br>_예: spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=.\worker\Microsoft.Spark.Worker_
| --files               | 각 실행기의 작업 디렉터리에 배치될 파일의 쉼표로 구분된 목록입니다.<br/><ul><li>이 옵션은 Yarn 모드에만 적용할 수 있습니다.</li><li>Hadoop과 비슷한 #으로 파일 이름 지정을 지원합니다.</br></ul>_예: <code>myLocalSparkApp.dll#appSeen.dll</code> 애플리케이션은 YARN에서 실행하는 경우 <code>myLocalSparkApp.dll</code>를 참조하려면 이름을 <code>appSeen.dll</code>로 사용해야 합니다._</li>
| --archives          | 각 실행기의 작업 디렉터리로 추출될 보관의 쉼표로 구분된 목록입니다.</br><ul><li>이 옵션은 Yarn 모드에만 적용할 수 있습니다.</li><li>Hadoop과 비슷한 #으로 파일 이름 지정을 지원합니다.</br></ul>_예: <code>hdfs://&lt;path to your worker file&gt;/Microsoft.Spark.Worker.zip#worker</code> 그러면 zip 파일이 <code>worker</code> 폴더에 복사되고 압축을 풉니다._</li>
| application-jar       | 애플리케이션 및 모든 종속성을 포함하여 번들로 제공되는 Jar의 경로입니다.</br>_Dp: hdfs://&lt;Jar 경로&gt;/microsoft-spark-&lt;version&gt;.jar_
| application-arguments | 주 클래스의 주 메서드에 전달된 인수입니다(있는 경우).</br>_예: hdfs://&lt;앱 경로&gt;/&lt;사용 중인 앱&gt;.zip &lt;앱 이름&gt; &lt;앱 인수&gt;_

> [!NOTE]
> `spark-submit`를 사용하여 애플리케이션을 시작하는 경우 `application-jar` 전에 모든 `--options`을 지정합니다. 지정하지 않으면 무시됩니다. 자세한 내용은 [`spark-submit` 옵션](https://spark.apache.org/docs/latest/submitting-applications.html) 및 [YARN에서 Spark 실행 세부 정보](https://spark.apache.org/docs/latest/running-on-yarn.html)을 참조하세요.

## <a name="frequently-asked-questions"></a>질문과 대답
### <a name="when-i-run-a-spark-app-with-udfs-i-get-a-filenotfoundexception-error-what-should-i-do"></a>UDF를 사용하여 Spark 앱을 실행하면 `FileNotFoundException' 오류가 발생합니다. 어떻게 해야 합니까?
> **오류:** [오류] [작업 실행자] [0] ProcessStream()이 다음 예외를 나타내며 실패함: System.IO.FileNotFoundException: 어셈블리 'mySparkApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null' 파일을 찾을 수 없음: 'mySparkApp.dll'

**대답:** `DOTNET_ASSEMBLY_SEARCH_PATHS` 환경 변수가 올바르게 설정되었는지 확인하세요. `mySparkApp.dll`이 포함된 경로여야 합니다.

### <a name="after-i-upgraded-my-net-for-apache-spark-version-and-reset-the-dotnet_worker_dir-environment-variable-why-do-i-still-get-the-following-ioexception-error"></a>Apache Spark 버전의 .NET을 업그레이드하고 `DOTNET_WORKER_DIR` 환경 변수를 다시 설정한 후에도 다음 `IOException` 오류가 계속 발생하는 이유는 무엇인가요?
> **오류:** 11.0 단계에서 작업 0.0 손실(TID 24, localhost, 실행기 드라이버): java.io.IOException: "Microsoft.Spark.Worker.exe" 프로그램을 실행할 수 없음: CreateProcess error=2, 지정한 파일을 시스템에서 찾을 수 없습니다.

**대답:** 최신 환경 변수 값을 사용할 수 있도록 PowerShell 창(또는 기타 명령 창)을 먼저 다시 시작하세요. 그런 다음, 프로그램을 시작합니다.

### <a name="after-submitting-my-spark-application-i-get-the-error-systemtypeloadexception-could-not-load-type-systemruntimeremotingcontextscontext"></a>Spark 애플리케이션을 제출한 후에 `System.TypeLoadException: Could not load type 'System.Runtime.Remoting.Contexts.Context'` 오류가 발생합니다.
> **오류:** [오류] [작업 실행자] [0] ProcessStream()이 다음 예외를 나타내며 실패함: System.TypeLoadException: 'mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=...' 어셈블리에서 'System.Runtime.Remoting.Contexts.Context' 형식을 로드할 수 없습니다.

**대답:** 사용 중인 `Microsoft.Spark.Worker` 버전을 확인하세요. **.NET Framework 4.6.1** 및 **.NET Core 2.1.x**의 두 가지 버전이 있습니다. 이 경우 `System.Runtime.Remoting.Contexts.Context`는 .NET Framework 전용이기 때문에 `Microsoft.Spark.Worker.net461.win-x64-<version>`([다운로드](https://github.com/dotnet/spark/releases)할 수 있음)을 사용해야 합니다.

### <a name="how-do-i-run-my-spark-application-with-udfs-on-yarn-which-environment-variables-and-parameters-should-i-use"></a>YARN에서 UDF를 사용하여 내 Spark 애플리케이션을 실행하는 방법은 무엇인가요? 어떤 환경 변수와 매개 변수를 사용해야 하나요?

**대답:** YARN에서 Spark 애플리케이션을 시작하려면 환경 변수를 `spark.yarn.appMasterEnv.[EnvironmentVariableName]`로 지정해야 합니다. `spark-submit`을 사용하는 예제는 아래를 참조하세요.

```powershell
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master yarn \
--deploy-mode cluster \
--conf spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=./worker/Microsoft.Spark.Worker-<version> \
--conf spark.yarn.appMasterEnv.DOTNET_ASSEMBLY_SEARCH_PATHS=./udfs \
--archives hdfs://<path to your files>/Microsoft.Spark.Worker.net461.win-x64-<version>.zip#worker,hdfs://<path to your files>/mySparkApp.zip#udfs \
hdfs://<path to jar file>/microsoft-spark-2.4.x-<version>.jar \
hdfs://<path to your files>/mySparkApp.zip mySparkApp
```

## <a name="next-steps"></a>다음 단계

* [.NET for Apache Spark 시작](../tutorials/get-started.md)
* [Windows에서 .NET for Apache Spark 애플리케이션 디버그](debug.md)
