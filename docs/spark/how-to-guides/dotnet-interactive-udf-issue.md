---
title: .NET for Apache Spark 대화형 환경에서 UDF 작성 및 호출
description: .NET for Apache Spark 대화형 셸에서 UDF를 작성하고 호출하는 방법을 알아봅니다.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 7f050b39b1d2f0e2f506c522259485d87c7a185a
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955012"
---
# <a name="write-and-call-udfs-in-net-for-apache-spark-interactive-environments"></a>.NET for Apache Spark 대화형 환경에서 UDF 작성 및 호출

이 문서에서는 .NET for Apache Spark 대화형 환경에서 UDF(사용자 정의 함수)를 사용하는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 구성 요소

1. [.NET Interactive](https://github.com/dotnet/interactive) 설치
2. [Jupyter Lab](https://jupyter.org/) 설치

## <a name="net-for-apache-spark-interactive-experience"></a>.NET for Apache Spark 대화형 환경

[.NET for Apache Spark](https://github.com/dotnet/spark)는 [.NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/)를 사용하여 Spark 내의 대화형 환경에 대한 .NET 지원을 제공합니다. Jupyter Notebook과 함께 .NET Interactive를 사용하도록 환경을 설정하는 방법을 알아보려면 [.NET Interactive 리포지토리](https://github.com/dotnet/interactive)를 참조하세요.

또한 [.NET for Apache Spark의 UDF serialization 관련 문서](udf-guide.md)에서 UDF란 무엇인지와 .NET for Apache Spark에서 UDF를 직렬화하는 방법을 살펴보는 것이 좋습니다.
이 가이드에서는 Jupyter Notebook을 이용하여 대화형 환경에서 UDF를 사용하는 방법을 설명합니다.

## <a name="define-a-udf-in-net-interactive"></a>.NET Interactive에서 UDF 정의

대화형 환경에서 셀은 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 반복의 일부로 제출되는 코드 조각으로 간주될 수 있습니다. 예를 들어 그 의미를 이해하기 위해 다음 Notebook을 살펴보겠습니다.

![Jupyter Notebook 셀](./media/dotnet-interactive/dotnet-interactive-cells.png)

빨간색 화살표로 표시된 각 블록은 단일 셀이거나 코드를 Spark에 제출하는 단일 작업입니다. 이제 사용자 지정 사용자 정의 개체를 참조하는 UDF를 정의할 때 참조하는 개체가 정의된 셀에서 UDF를 정의해야 합니다. 예를 들어 다음 코드를 살펴봅시다.

![제대로 실행되는 UDF](./media/dotnet-interactive/working-udf.png)

## <a name="call-a-udf-on-a-dataframe"></a>DataFrame에서 UDF 호출

이전에 정의한 UDF를 `DataFrame`에서 호출하는 경우 이전 예제와 같이 UDF를 호출하기 전에 UDF가 이전에 제출한 셀에 정의되어 있는지 확인하는 것이 중요합니다.

이제 UDF가 정의된 셀에서 UDF를 호출하면 어떻게 되는지 살펴봅시다.

![UDF 호출 실패](./media/dotnet-interactive/udf_fails.png)

위에 강조 표시된 오류는 먼저 UDF 어셈블리를 컴파일하고 작업자에게 제공해야 DataFrame에서 호출할 수 있기 때문입니다.

이상으로 .NET for Apache Spark 대화형 환경(예: [Azure Synapse Notebooks](https://docs.microsoft.com/azure/synapse-analytics/spark/apache-spark-development-using-notebooks))에서 UDF를 구현하는 동안 유의해야 할 몇 가지 중요한 사항을 살펴보았습니다.

## <a name="faqs"></a>FAQ

1. **사용자 지정 사용자 정의 개체를 참조하는 UDF가 `Type Submission#_ is not marked as serializable` 오류를 throw하는 이유는 무엇인가요?**
    .NET Interactive는 제출되는 각 셀을 고유하게 식별하기 위해 셀 제출 번호의 래퍼 클래스를 사용하여 각 셀을 래핑합니다. [관련 가이드](udf-guide.md)에 자세히 설명된 것처럼, 사용자 지정 개체를 참조하는 UDF가 직렬화되는 경우 해당 대상도 serialization되도록 선택되므로, .NET Interactive의 경우 사용자 지정 개체가 정의된 셀의 래퍼 클래스로 래핑됩니다.
    이제 Notebook에서 해당 동작이 UDF 정의에 미치는 영향을 살펴봅시다.

    ![UDF serialization 오류](./media/dotnet-interactive/udf-serialization-error.png)

    `udf2_fails`의 경우에서 확인할 수 있듯이, `Submission#7` 유형이 serializable로 표시되지 않는다는 오류 메시지가 나타납니다. 이 오류는 .NET Interactive가 셀에 정의된 모든 개체를 해당 `Submission#` 클래스로 래핑하므로 개체가 즉석에서 생성되어 `Serializable`로 표시되지 않기 때문입니다.

    따라서 **사용자 지정 개체를 참조하는 UDF가 해당 개체와 동일한 셀에서 정의되어야 합니다**.

2. **브로드캐스트 변수가 .NET Interactive에서 작동하지 않는 이유는 무엇인가요?**
    앞서 설명한 이유로 브로드캐스트 변수는 .NET Interactive에서 작동하지 않습니다. [브로드캐스트 변수 관련 가이드](broadcast-guide.md)에서 브로드캐스트 변수란 무엇인지와 브로드캐스트 변수를 사용하는 방법을 자세히 살펴보는 것이 좋습니다. 브로드캐스트 변수가 대화형 시나리오에서 작동하지 않는 이유는 셀에 정의된 각 개체를 해당 셀 제출 클래스와 함께 추가하는 .NET interactive의 디자인에 따라 개체가 serializable로 표시되지 않으므로 앞서 확인한 것과 동일한 예외가 발생하여 실패하기 때문입니다.
    다음 예제를 사용하여 좀 더 자세히 살펴봅시다.

    ![브로드캐스트 변수 오류](./media/dotnet-interactive/broadcast-fails.png)

    이전 섹션에서 권장한 것처럼 UDF와 UDF가 참조하는 개체(이 예제에서는 브로드캐스트 변수)를 동일한 셀에서 정의하지만 `Microsoft.Spark.Sql.Session`이 serializable로 표시되지 않는다는 `SerializationException` 오류가 여전히 표시됩니다. 이 오류는 컴파일러가 `bv` 브로드캐스트 변수 개체를 직렬화하려고 할 때 개체 이름이 [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) 개체 `spark`와 함께 추가되므로 serializable로 표시되어야 함을 발견했기 때문입니다. 다음 셀 제출의 디컴파일된 어셈블리를 살펴보면 더 쉽게 오류를 확인할 수 있습니다.

    ![디컴파일된 어셈블리 코드](./media/dotnet-interactive/decompiledAssembly.png)

    [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) 클래스를 `[Serializable]`로 표시하면 코드가 제대로 실행되지만, SparkSession 개체를 직렬화하는 기능을 사용자에게 제공할 경우 바람직하지 않은 이상한 동작이 생성될 수 있으므로 이상적인 솔루션은 아닙니다. 이 오류는 [알려진 문제](https://github.com/dotnet/spark/issues/619)이며, 향후 버전에서 해결될 예정입니다.
