---
title: .NET for Apache Spark에서 UDF(사용자 정의 함수) 만들기
description: .NET for Apache Spark 애플리케이션에서 UDF(사용자 정의 함수)를 구현하는 방법을 알아봅니다.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 97afda8ed17d3719c534d72ad3ad026745a70922
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620926"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a>.NET for Apache Spark에서 UDF(사용자 정의 함수) 만들기

이 문서에서는 .NET for Apache Spark에서 UDF(사용자 정의 함수)를 사용하는 방법을 알아봅니다. [UDF](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html)는 사용자 지정 함수를 사용하여 시스템의 기본 제공 기능을 확장할 수 있는 Spark 기능입니다. UDF는 테이블 내에 있는 단일 행의 값을 변환하여 UDF에 정의된 논리를 기준으로 행당 하나의 해당 출력 값을 생성합니다.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="define-udfs"></a>UDF 정의

다음 UDF 정의를 검토하세요.

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

UDF는 [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)의 [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) 형식으로 `string`을 입력으로 사용하고 입력 앞에 `hello`를 추가한 `string`을 반환합니다.

다음 DataFrame `df`에는 이름 목록이 포함되어 있습니다.

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

이제 DataFrame `df`에 위에서 정의한 `udf`를 적용하겠습니다.

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

다음 DataFrame `udfResult`는 UDF의 결과입니다.

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

UDF를 구현하는 방법을 더 잘 이해하려면 GitHub에서 [UDF 도우미 함수](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) 및 [예제](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49)를 살펴보세요.

## <a name="udf-serialization"></a>UDF serialization

UDF는 작업자에서 실행해야 하는 함수이므로 직렬화하고 드라이버에서 페이로드의 일부로 작업자에 보내야 합니다. 메서드에 대한 참조인 [대리자](../../csharp/programming-guide/delegates/index.md)는 직렬화되어야 하며, 현재 대리자가 인스턴스 메서드를 호출하는 클래스 인스턴스인 해당 [대상](xref:System.Delegate.Target%2A)도 직렬화해야 합니다. UDF serialization을 수행하는 방법을 더 잘 이해하려면 [GitHub의 이 코드 예제](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149)를 검토하세요.

.NET for Apache Spark는 대리자 직렬화를 지원하지 않는 .NET Core를 사용합니다. 대신 리플렉션을 사용하여 대리자가 정의된 대상을 직렬화합니다. 공통 범위에 여러 대리자를 정의하는 경우 해당 대리자는 serialization을 위한 리플렉션 대상이 되는 공유 닫기를 가집니다.

### <a name="serialization-example"></a>직렬화 예제

다음 코드 조각에서는 해당하는 문자열을 결과로 반환하는 두 개의 함수 대리자에서 참조되는 두 개의 문자열 변수를 정의합니다.

```csharp
using System;

public class C {
    public void M() {
        string s1 = "s1";
        string s2 = "s2";
        Func<string, string> a = str => s1;
        Func<string, string> b = str => s2;
    }
}
```

위의 C# 코드는 컴파일러에서 다음 C# 디스어셈블리(크레딧 소스: [sharplab.io](https://sharplab.io)) 코드를 생성합니다.

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        public string s2;

        internal string <M>b__0(string str)
        {
            return s1;
        }

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        <>c__DisplayClass0_.s2 = "s2";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_.<M>b__1);
    }
}
```

`func`와 `func2`는 모두 동일한 닫기 `<>c__DisplayClass0_0`을 공유하며, 이 닫기는 대리자 `func` 및 `func2`를 직렬화할 때 직렬화되는 대상입니다. `Func<string, string> a`는 `s1`만 참조하지만 바이트를 작업자에 보낼 때 `s2`도 직렬화됩니다.

이로 인해 [브로드캐스트 변수](broadcast-guide.md)를 사용하는 경우처럼 런타임에 예기치 않은 동작이 발생할 수 있습니다. 따라서 함수에 사용되는 변수의 표시를 해당 함수의 범위로 제한하는 것이 좋습니다.

다음 코드 조각은 원하는 serialization 동작을 구현하기 위한 권장되는 방법입니다.

```csharp
using System;

public class C {
    public void M() {
        {
            string s1 = "s1";
            Func<string, string> a = str => s1;
        }
        {
            string s2 = "s2";
            Func<string, string> b = str => s2;
        }
    }
}
```

위의 C# 코드는 컴파일러에서 다음 C# 디스어셈블리(크레딧 소스: [sharplab.io](https://sharplab.io)) 코드를 생성합니다.

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        internal string <M>b__0(string str)
        {
            return s1;
        }
    }

    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_1
    {
        public string s2;

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        <>c__DisplayClass0_1 <>c__DisplayClass0_2 = new <>c__DisplayClass0_1();
        <>c__DisplayClass0_2.s2 = "s2";
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_2.<M>b__1);
    }
}
```

`func` 및 `func2`는 더 이상 닫기를 공유하지 않으며 각각 별도의 닫기 `<>c__DisplayClass0_0` 및 `<>c__DisplayClass0_1`을 가집니다. serialization의 대상으로 사용되는 경우 참조된 변수 외에는 어느 것도 대리자를 위해 직렬화되지 않습니다. 공동 범위에 여러 UDF를 구현할 때는 이 동작을 유념해야 합니다.

## <a name="some-spark-udf-caveats"></a>몇 가지 Spark UDF 주의 사항

* UDF에 null 값을 사용하면 예외를 throw할 수 있습니다. 해당 예외는 개발자가 처리해야 합니다.
* UDF는 Spark의 기본 제공 함수에서 제공하는 최적화를 사용하지 않으므로 가능한 한 기본 제공 함수를 사용하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계

* [.NET for Apache Spark 시작](../tutorials/get-started.md)
* [Windows에서 .NET for Apache Spark 애플리케이션 디버그](debug.md)
