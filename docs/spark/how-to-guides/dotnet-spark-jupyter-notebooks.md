---
title: Jupyter Notebook 사용
titleSuffix: .NET for Apache Spark
description: Jupyter Notebook, Jupyter Lab 또는 VS Code(Visual Studio Code)와 같은 대화형 환경에서 .NET for Apache Spark 사용
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: eb285465fcacc3e7d4ee60765c30497dcefbc737
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441065"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a>Jupyter Notebook에서 .NET for Apache Spark 사용

이 문서에서는 .NET Interactive를 사용하여 Jupyter Notebook 및 VS Code(Visual Studio Code)에서 .NET for Apache Spark 작업을 대화형으로 실행하는 방법을 알아봅니다.

## <a name="about-jupyter"></a>Jupyter 정보

[Jupyter](https://jupyter.org/)는 사용자가 대화형으로 애플리케이션 프로토타입을 작성하고 개발할 수 있는 방법을 제공하는 오픈 소스 플랫폼 간 컴퓨팅 환경입니다. Jupyter Notebook, Jupyter Lab, VS Code 등의 다양한 인터페이스를 통해 Jupyter를 조작할 수 있습니다.

.NET 컨텍스트에서 .NET Core 전역 도구인 [.NET Interactive](https://github.com/dotnet/interactive)는 Jupyter Notebook과 같은 대화형 컴퓨팅 환경에서 .NET 코드(C#/F#)를 작성하기 위한 커널을 제공합니다.

## <a name="prerequisites"></a>필수 구성 요소

- [.NET Core 3.1 SDK](../../core/install/index.yml)
- [Apache Spark](https://spark.apache.org/downloads.html)
- [Apache Spark .NET Worker](https://github.com/dotnet/spark/releases)

.NET for Apache Spark 환경을 설정하는 방법에 대한 자세한 내용은 [시작하기 자습서](../tutorials/get-started.md)를 참조하세요.

## <a name="prepare-environment"></a>환경 준비

Jupyter Notebook을 사용하려면 두 가지 항목이 필요합니다.

1. [.NET Interactive 전역 .NET 도구](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)를 설치합니다.
1. `Microsoft.Spark` NuGet 패키지를 다운로드합니다.
    1. [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지 페이지로 이동합니다.

        > [!IMPORTANT]
        > 기본적으로 최신 버전의 패키지가 다운로드됩니다. **다운로드한 버전이 Apache Spark .NET Worker와 동일한지 확인합니다.**

    1. **정보** 창에서 **패키지 다운로드** 를 선택하여 최신 버전의 패키지를 다운로드합니다. 패키지 이름은 *microsoft.spark.[PACKAGE-VERSION].nupkg* 와 유사합니다.
    1. 다운로드한 패키지의 압축을 풉니다. 압축을 푼 디렉터리에 *jars* 라는 하위 디렉터리가 있습니다. 나중에 사용되므로 경로를 기록해 둡니다.

## <a name="start-net-for-apache-spark"></a>.NET for Apache Spark 시작

다음 명령을 실행하여 .NET for Apache Spark를 디버그 모드로 시작합니다. `spark-submit` 명령은 프로세스를 시작하고 [SparkSession](xref:Microsoft.Spark.Sql.SparkSession)의 연결을 기다립니다. 사용 중인 .NET for Apache Spark 버전에 해당하는 `microsoft-spark-<version>.jar` 경로를 입력해야 합니다.

**Ubuntu**

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

**Windows**

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a>Notebook 만들기

다른 인터페이스를 사용하여 Jupyter를 조작할 수 있습니다. 브라우저 기반 인터페이스가 필요하면 Jupyter Notebook 또는 Jupyter Lab을 사용합니다. 로컬 편집기 환경이 필요하면 VS Code를 사용합니다.

### <a name="jupyter-notebooks--jupyter-lab"></a>Jupyter Notebook 및 Jupyter Lab

1. 다른 명령 프롬프트에서 아래 명령 중 하나를 사용하여 Jupyter Notebook 또는 Jupyter Lab을 시작합니다.

    **Jupyter Notebook**

    ```bash
    jupyter notebook
    ```

    **Jupyter Lab**

    ```bash
    jupyter lab
    ```

    위 명령은 Jupyter Notebook 또는 Jupyter Lab 인터페이스를 사용하여 브라우저 창을 시작합니다.

1. 브라우저에서 새 Notebook을 만듭니다.

    **Jupyter Notebook**

    **새로 만들기 > .NET(C#)** 또는 **새로 만들기 > .NET(F#)** 을 선택합니다.

    **Jupyter Lab**

    시작 관리자 창에서 **.NET(C#)** 또는 **.NET(F#)** 을 선택합니다.

### <a name="visual-studio-code-preview"></a>Visual Studio Code(미리 보기)

> [!IMPORTANT]
> VS Code에서 Jupyter Notebook을 사용하려면 다음을 설치해야 합니다.
>
>- [VS Code Insiders](https://code.visualstudio.com/insiders/)
>- [.NET Interactive Notebook 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. VS Code를 엽니다.
1. 명령 팔레트를 엽니다(**보기 > 명령 팔레트**).

    명령 팔레트가 표시되면 다음 명령을 입력하여 새 .NET Interactive Notebook을 만듭니다.

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    또는 *.ipynb* 확장을 사용하여 기존 .NET Interactive Notebook을 열려면 다음 명령을 사용합니다.

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a>Spark 세션 초기화

1. Notebook이 열리면 `Microsoft.Spark` NuGet 패키지를 설치합니다. 설치한 버전이 .NET Worker와 동일한지 확인합니다.

    ```text
    #r "nuget:Microsoft.Spark, 0.12.1"
    ```

1. 다음 using 문을 Notebook에 추가합니다.

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. [SparkSession](xref:Microsoft.Spark.Sql.SparkSession)을 초기화합니다.

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

Notebook이 다음 이미지와 같이 표시됩니다. 예제에서는 VS Code를 사용하지만 Jupyter Notebook과 Jupyter Lab도 거의 동일하게 표시됩니다.

> [!div class="mx-imgBorder"]
![.NET for Apache Spark Jupyter Notebook VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)

## <a name="next-steps"></a>다음 단계

- [.NET for Apache Spark 시작](../tutorials/get-started.md)
- [.NET for Apache Spark 및 ML.NET을 사용하여 감정 예측](../tutorials/ml-sentiment-analysis.md)
- .NET Interactive에 대한 자세한 내용은 [.NET Interactive 설명서](https://github.com/dotnet/interactive/blob/main/docs/README.md)를 참조하세요.
