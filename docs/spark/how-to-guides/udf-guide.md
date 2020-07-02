---
title: .NET for Apache Spark에서 UDF(사용자 정의 함수) 만들기
description: .NET for Apache Spark 애플리케이션에서 UDF(사용자 정의 함수)를 구현하는 방법을 알아봅니다.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: fe3dec187f94f84adb1217c39ff6aabc4b4db1c5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142019"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a><span data-ttu-id="6a871-103">.NET for Apache Spark에서 UDF(사용자 정의 함수) 만들기</span><span class="sxs-lookup"><span data-stu-id="6a871-103">Create user-defined functions (UDF) in .NET for Apache Spark</span></span>

<span data-ttu-id="6a871-104">이 문서에서는 .NET for Apache Spark에서 UDF(사용자 정의 함수)를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-104">In this article, you learn how to use user-defined functions (UDF) in .NET for Apache Spark.</span></span> <span data-ttu-id="6a871-105">[UDF](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html)는 사용자 지정 함수를 사용하여 시스템의 기본 제공 기능을 확장할 수 있는 Spark 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-105">[UDFs)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) are a Spark feature that allow you to use custom functions to extend the system's built-in functionality.</span></span> <span data-ttu-id="6a871-106">UDF는 테이블 내에 있는 단일 행의 값을 변환하여 UDF에 정의된 논리를 기준으로 행당 하나의 해당 출력 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-106">UDFs transform values from a single row within a table to produce a single corresponding output value per row based on the logic defined in the UDF.</span></span>

## <a name="define-udfs"></a><span data-ttu-id="6a871-107">UDF 정의</span><span class="sxs-lookup"><span data-stu-id="6a871-107">Define UDFs</span></span>

<span data-ttu-id="6a871-108">다음 UDF 정의를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="6a871-108">Review the following UDF definition:</span></span>

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

<span data-ttu-id="6a871-109">UDF는 [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)의 [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) 형식으로 `string`을 입력으로 사용하고 입력 앞에 `hello`를 추가한 `string`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-109">The UDF takes a `string` as an input in the form of a [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) of a [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) and returns a `string` with `hello` appended in front of the input.</span></span>

<span data-ttu-id="6a871-110">다음 DataFrame `df`에는 이름 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-110">The following DataFrame `df` contains a list of names:</span></span>

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

<span data-ttu-id="6a871-111">이제 DataFrame `df`에 위에서 정의한 `udf`를 적용하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-111">Now let's apply the above defined `udf` to the DataFrame `df`:</span></span>

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

<span data-ttu-id="6a871-112">다음 DataFrame `udfResult`는 UDF의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-112">The following DataFrame `udfResult` is the result of the UDF:</span></span>

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

<span data-ttu-id="6a871-113">UDF를 구현하는 방법을 더 잘 이해하려면 GitHub에서 [UDF 도우미 함수](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) 및 [예제](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49)를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="6a871-113">To better understand how to implement UDFs, review the [UDF helper functions](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) and [examples](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) on GitHub.</span></span>

## <a name="udf-serialization"></a><span data-ttu-id="6a871-114">UDF serialization</span><span class="sxs-lookup"><span data-stu-id="6a871-114">UDF serialization</span></span>

<span data-ttu-id="6a871-115">UDF는 작업자에서 실행해야 하는 함수이므로 직렬화하고 드라이버에서 페이로드의 일부로 작업자에 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-115">Because UDFs are functions that need to be executed on workers, they have to be serialized and sent to the workers as part of the payload from the driver.</span></span> <span data-ttu-id="6a871-116">메서드에 대한 참조인 [대리자](../../csharp/programming-guide/delegates/index.md)는 직렬화되어야 하며, 현재 대리자가 인스턴스 메서드를 호출하는 클래스 인스턴스인 해당 [대상](xref:System.Delegate.Target%2A)도 직렬화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-116">The [delegate](../../csharp/programming-guide/delegates/index.md), which is a reference to the method, needs to be serialized as well as its [target](xref:System.Delegate.Target%2A), which is the class instance on which the current delegate invokes the instance method.</span></span> <span data-ttu-id="6a871-117">UDF serialization을 수행하는 방법을 더 잘 이해하려면 [GitHub의 이 코드 예제](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="6a871-117">Review this [code example in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) to get a better understanding of how UDF serialization is being done.</span></span>

<span data-ttu-id="6a871-118">.NET for Apache Spark는 대리자 직렬화를 지원하지 않는 .NET Core를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-118">.NET for Apache Spark uses .NET Core, which doesn't support serializing delegates.</span></span> <span data-ttu-id="6a871-119">대신 리플렉션을 사용하여 대리자가 정의된 대상을 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-119">Instead, reflection is used to serialize the target where the delegate is defined.</span></span> <span data-ttu-id="6a871-120">공통 범위에 여러 대리자를 정의하는 경우 해당 대리자는 serialization을 위한 리플렉션 대상이 되는 공유 닫기를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-120">When multiple delegates are defined in a common scope, they have a shared closure that becomes the target of reflection for serialization.</span></span>

### <a name="serialization-example"></a><span data-ttu-id="6a871-121">직렬화 예제</span><span class="sxs-lookup"><span data-stu-id="6a871-121">Serialization example</span></span>

<span data-ttu-id="6a871-122">다음 코드 조각에서는 해당하는 문자열을 결과로 반환하는 두 개의 함수 대리자에서 참조되는 두 개의 문자열 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-122">The following code snippet defines two string variables that are being referenced in two function delegates that return the respective strings as a result:</span></span>

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

<span data-ttu-id="6a871-123">위의 C# 코드는 컴파일러에서 다음 C# 디스어셈블리(크레딧 소스: [sharplab.io](https://sharplab.io)) 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-123">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

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

<span data-ttu-id="6a871-124">`func`와 `func2`는 모두 동일한 닫기 `<>c__DisplayClass0_0`을 공유하며, 이 닫기는 대리자 `func` 및 `func2`를 직렬화할 때 직렬화되는 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-124">Both `func` and `func2` share the same closure `<>c__DisplayClass0_0`, which is the target that is serialized when serializing the delegates `func` and `func2`.</span></span> <span data-ttu-id="6a871-125">`Func<string, string> a`는 `s1`만 참조하지만 바이트를 작업자에 보낼 때 `s2`도 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-125">Even though `Func<string, string> a` is only referencing `s1`, `s2` is also serialized when the bytes are sent to the workers.</span></span>

<span data-ttu-id="6a871-126">이로 인해 [브로드캐스트 변수](broadcast-guide.md)를 사용하는 경우처럼 런타임에 예기치 않은 동작이 발생할 수 있습니다. 따라서 함수에 사용되는 변수의 표시를 해당 함수의 범위로 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-126">This can lead to some unexpected behaviors at runtime (like in the case of using [broadcast variables](broadcast-guide.md)), which is why we recommend that you restrict the visibility of the variables used in a function to that function's scope.</span></span>

<span data-ttu-id="6a871-127">다음 코드 조각은 원하는 serialization 동작을 구현하기 위한 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-127">The following code snippet is the recommended way to implement the desired serialization behavior:</span></span>

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

<span data-ttu-id="6a871-128">위의 C# 코드는 컴파일러에서 다음 C# 디스어셈블리(크레딧 소스: [sharplab.io](https://sharplab.io)) 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-128">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

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

<span data-ttu-id="6a871-129">`func` 및 `func2`는 더 이상 닫기를 공유하지 않으며 각각 별도의 닫기 `<>c__DisplayClass0_0` 및 `<>c__DisplayClass0_1`을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-129">Notice that `func` and `func2` no longer share a closure, and they have their own separate closures `<>c__DisplayClass0_0` and `<>c__DisplayClass0_1` respectively.</span></span> <span data-ttu-id="6a871-130">serialization의 대상으로 사용되는 경우 참조된 변수 외에는 어느 것도 대리자를 위해 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-130">When used as the target for serialization, nothing other than the referenced variables will get serialized for the delegate.</span></span> <span data-ttu-id="6a871-131">공동 범위에 여러 UDF를 구현할 때는 이 동작을 유념해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-131">This behavior is important to keep in mind while implementing multiple UDFs in a common scope.</span></span>

## <a name="some-spark-udf-caveats"></a><span data-ttu-id="6a871-132">몇 가지 Spark UDF 주의 사항</span><span class="sxs-lookup"><span data-stu-id="6a871-132">Some Spark UDF caveats</span></span>

* <span data-ttu-id="6a871-133">UDF에 null 값을 사용하면 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-133">Null values in UDFs can throw exceptions.</span></span> <span data-ttu-id="6a871-134">해당 예외는 개발자가 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-134">It's the responsibility of the developer to handle them.</span></span>
* <span data-ttu-id="6a871-135">UDF는 Spark의 기본 제공 함수에서 제공하는 최적화를 사용하지 않으므로 가능한 한 기본 제공 함수를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a871-135">UDFs don't leverage the optimizations provided by Spark's built-in functions, so it's recommended to use built-in functions where possible.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6a871-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6a871-136">Next steps</span></span>

* [<span data-ttu-id="6a871-137">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="6a871-137">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="6a871-138">Windows에서 .NET for Apache Spark 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="6a871-138">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
