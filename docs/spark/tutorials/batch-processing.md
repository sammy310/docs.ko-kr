---
title: .NET for Apache Spark를 사용한 일괄 처리 자습서
description: .NET for Apache Spark를 사용하여 일괄 처리하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 06/25/2020
ms.topic: tutorial
ms.openlocfilehash: dbc3ab5cc4bd7f438e9f3f8e5d36c764d785ce4b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618287"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a>자습서: .NET for Apache Spark를 사용한 일괄 처리

이 자습서에서는 .NET for Apache Spark를 사용하여 일괄 처리하는 방법을 알아봅니다. 일괄 처리는 미사용 데이터의 변환으로 원본 데이터가 이미 데이터 스토리지에 로드되었음을 의미합니다.

일괄 처리는 일반적으로 추가 분석을 준비해야 하는 대량의 플랫 데이터 세트를 대상으로 수행합니다. 로그 처리 및 데이터 웨어하우징은 일반적인 일괄 처리 시나리오입니다. 이 시나리오에서는 각 프로젝트가 분기된 횟수 또는 프로젝트 업데이트 후 경과한 기간과 같이 GitHub 프로젝트 정보를 분석합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * .NET for Apache Spark 애플리케이션 만들기 및 실행
> * DataFrame으로 데이터를 읽고 분석 준비
> * Spark SQL을 사용하여 데이터 처리

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>사전 요구 사항

.NET for Apache Spark를 처름 사용하는 경우 [.NET for Apache Spark 시작](get-started.md) 자습서를 확인하여 환경을 준비하고 첫 번째 .NET for Apache Spark 애플리케이션을 실행하는 방법을 알아봅니다.

## <a name="download-the-sample-data"></a>샘플 데이터 다운로드

[GHTorrent](http://ghtorrent.org/)는 프로젝트, 커밋 및 감시자 관련 정보와 같은 모든 공용 GitHub 이벤트를 모니터링하고 데이터베이스에 이벤트와 이벤트 구조를 저장합니다. 다른 기간에 걸쳐 수집된 데이터는 다운로드 가능한 보관 파일로 제공됩니다. 덤프 파일이 매우 크기 때문에 이 가이드에서는 GitHub에서 다운로드할 수 있는 [잘린 버전의 덤프 파일](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv)을 사용합니다.

> [!NOTE]
> GHTorrent 데이터 세트는 이중 라이선스 체계([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus))를 통해 배포됩니다. 비상업적 용도(교육, 연구 또는 개인 용도를 포함하지만 이에 국한되지 않음)의 경우 데이터 세트는 [CC-BY-SA 라이선스](https://creativecommons.org/licenses/by-sa/4.0/)를 통해 배포됩니다.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. 명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   `dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다. `-o` 매개 변수는 앱이 저장되는 *mySparkBatchApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다. `cd mySparkBatchApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.

1. 앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다. 콘솔에서 다음 명령을 실행합니다.

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a>SparkSession 만들기

1. 다음 추가 `using` 문을 *mySparkBatchApp*에서 *Program.cs* 파일의 맨 위에 추가합니다.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. 프로젝트 네임스페이스에 다음 코드를 추가합니다. *s_referenceData*는 나중에 프로그램에서 날짜를 기준으로 필터링하는 데 사용됩니다.

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. Main 메서드 내에 다음 코드를 추가하여 새 SparkSession을 설정합니다. SparkSession은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다. `spark` 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a>데이터 준비

1. 입력 파일을 명명된 열로 구성된 데이터의 분산된 컬렉션인 `DataFrame`으로 읽어 들입니다. <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A> 사용을 통해 데이터의 열을 설정할 수 있습니다. <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> 메서드를 사용하여 DataFrame에 데이터를 표시합니다. CSV 파일 경로를 다운로드한 GitHub 데이터의 위치로 업데이트해야 합니다.

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> 메서드를 사용하여 NA(null) 값이 있는 행을 삭제하고 <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> 메서드를 사용하여 데이터에서 특정 열을 제거합니다. 이렇게 하면 최종 분석과 관련이 없는 null 데이터 또는 열을 분석하려 할 때 오류를 방지할 수 있습니다.

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a>데이터 분석

Spark SQL을 사용하면 데이터에 대한 SQL 호출을 수행할 수 있습니다. 사용자 정의 함수와 Spark SQL을 결합하여 사용자 정의 함수를 DataFrame의 모든 행에 적용하는 것이 일반적입니다.

특히 `spark.Sql`을 호출하여 다른 유형의 앱에서 볼 수 있는 표준 SQL 호출을 모방할 수 있습니다. 또한 <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> 및 <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A>와 같은 메서드를 호출하여 데이터의 결합, 필터링 및 계산 수행을 할 수 있습니다.

이 앱의 목표는 GitHub 프로젝트 데이터에 관한 인사이트를 얻는 것입니다. 프로그램에 다음 코드 조각을 추가하여 데이터를 분석합니다.

1. 다음 코드 블록을 추가하여 각 언어가 분기된 횟수를 확인합니다. 먼저 데이터를 언어별로 그룹화합니다. 그런 다음 각 언어의 평균 분기 횟수를 가져옵니다.

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. 다음 코드 블록을 추가하여 평균 분기 횟수를 내림차순으로 정렬하고 가장 많이 분기된 언어를 확인합니다. 가장 많은 분기 횟수가 먼저 표시됩니다.

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. 다음 코드 블록은 최근 프로젝트가 어떻게 업데이트되었는지 보여줍니다. *MyUDF*라는 새 사용자 정의 함수를 등록하고 자습서의 시작 부분에 선언된 날짜인 *s_referenceDate*와 비교합니다. 각 프로젝트의 날짜가 참조 날짜와 비교됩니다. 그런 다음 Spark SQL을 사용하여 데이터의 각 행에서 UDF를 호출하고 데이터 세트의 각 프로젝트를 분석합니다.

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. `spark.Stop()`을 호출하여 SparkSession을 종료합니다.

## <a name="use-spark-submit-to-run-your-app"></a>spark-submit을 사용하여 앱 실행

1. 다음 명령을 사용하여 .NET 앱을 빌드합니다.

   ```dotnetcli
   dotnet build
   ```

1. `spark-submit`을 사용하여 앱을 실행합니다. 다음 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다.

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a>코드 가져오기

GitHub에서 [전체 솔루션](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs)을 볼 수 있습니다.

## <a name="next-steps"></a>다음 단계

다음 문서로 이동하면 .NET for Apache Spark를 사용하여 스트리밍 데이터를 처리하는 방법을 알아볼 수 있습니다.
> [!div class="nextstepaction"]
> [자습서: .NET for Apache Spark를 사용한 구조적 스트리밍](streaming.md)
