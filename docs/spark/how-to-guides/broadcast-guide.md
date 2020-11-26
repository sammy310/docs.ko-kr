---
title: Apache Spark용으로 .NET에서 브로드캐스트 변수 사용
description: .NET에서 Apache Spark 애플리케이션용으로 브로드캐스트 변수를 사용하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: ca6dab01cbd639594da0b51f145272a9a150e93c
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687755"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a><span data-ttu-id="968eb-103">Apache Spark용으로 .NET에서 브로드캐스트 변수 사용</span><span class="sxs-lookup"><span data-stu-id="968eb-103">Use broadcast variables in .NET for Apache Spark</span></span>

<span data-ttu-id="968eb-104">이 문서에서는 .NET에서 Apache Spark용으로 브로드캐스트 변수를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-104">In this article, you learn how to use broadcast variables in .NET for Apache Spark.</span></span> <span data-ttu-id="968eb-105">[Apache Spark의 브로드캐스트 변수](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables)는 읽기 전용으로 사용할 변수를 실행기에서 공유하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-105">[Broadcast variables in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) are mechanisms for sharing variables across executors that are meant to be read-only.</span></span> <span data-ttu-id="968eb-106">브로드캐스트 변수를 사용하면 작업으로 복사본을 전달하는 대신 각 머신에 캐시된 읽기 전용 변수를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-106">Broadcast variables allow you to keep a read-only variable cached on each machine rather than shipping a copy of it with tasks.</span></span> <span data-ttu-id="968eb-107">브로드캐스트 변수를 사용하여 효율적인 방식으로 모든 노드에 대규모 입력 데이터 세트의 사본을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-107">You can use broadcast variables to give every node a copy of a large input dataset in an efficient manner.</span></span>

<span data-ttu-id="968eb-108">데이터는 한 번만 전송되기 때문에, 브로드캐스트 변수는 각 작업에서 실행기에 전달되는 지역 변수와 비교할 때 성능상의 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-108">Because the data is sent only once, broadcast variables have performance benefits when compared to local variables that are shipped to the executors with each task.</span></span> <span data-ttu-id="968eb-109">브로드캐스트 변수 및 이 변수를 사용하는 이유를 더 깊이 있게 이해하려면 [공식 브로드캐스트 변수 설명서](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="968eb-109">Refer to the [official broadcast variable documentation](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) to get a deeper understanding of broadcast variables and why they are used.</span></span>

## <a name="create-broadcast-variables"></a><span data-ttu-id="968eb-110">브로드캐스트 변수 만들기</span><span class="sxs-lookup"><span data-stu-id="968eb-110">Create broadcast variables</span></span>

<span data-ttu-id="968eb-111">브로드캐스트 변수를 만들려면 변수 `v`에 대해 `SparkContext.Broadcast(v)`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-111">To create a broadcast variable, call `SparkContext.Broadcast(v)` for any variable `v`.</span></span> <span data-ttu-id="968eb-112">브로드캐스트 변수는 변수 `v` 주위의 래퍼이며, `Value()` 메서드를 호출하여 이 변수의 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-112">The broadcast variable is a wrapper around the variable `v`, and its value can be accessed by calling the `Value()` method.</span></span>

<span data-ttu-id="968eb-113">다음 코드 조각에서는 문자열 변수 `v`를 만듭니다. `SparkContext.Broadcast(v)`를 호출하면 브로드캐스트 변수 `bv`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-113">In the following code snippet, a string variable `v` is created, and a broadcast variable `bv` is created when `SparkContext.Broadcast(v)`is called.</span></span> <span data-ttu-id="968eb-114">문자열 `Broadcast`에 대한 형식 매개 변수는 브로드캐스트 중인 변수의 형식과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-114">Notice the type parameter for `Broadcast`, string, matches the type of the variable being broadcasted.</span></span> <span data-ttu-id="968eb-115">UDF(사용자 정의 함수)는 `bv`의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-115">The user-defined function (UDF) returns the value of `bv`.</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a><span data-ttu-id="968eb-116">브로드캐스트 변수 삭제</span><span class="sxs-lookup"><span data-stu-id="968eb-116">Delete broadcast variables</span></span>

<span data-ttu-id="968eb-117">`Destroy()` 메서드를 호출하여 모든 실행기에서 브로드캐스트 변수를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-117">The broadcast variable can be deleted from all executors by calling the `Destroy()` method.</span></span>

```csharp
bv.Destroy();
```

<span data-ttu-id="968eb-118">`Destroy()`는 브로드캐스트 변수와 관련된 모든 데이터 및 메타데이터를 삭제하므로 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-118">`Destroy()` deletes all data and metadata related to the broadcast variable and should be used with caution.</span></span> <span data-ttu-id="968eb-119">브로드캐스트 변수가 제거되면 이 변수를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-119">Once a broadcast variable is destroyed, it can't be used again.</span></span>

## <a name="limit-broadcast-variable-scope-in-udfs"></a><span data-ttu-id="968eb-120">UDF에서 브로드캐스트 변수 범위 제한</span><span class="sxs-lookup"><span data-stu-id="968eb-120">Limit broadcast variable scope in UDFs</span></span>

<span data-ttu-id="968eb-121">UDF에 브로드캐스트 변수를 사용할 때는 변수의 범위를 변수가 참조하는 UDF로만 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-121">When you use broadcast variables in UDFs, you need to limit the scope of the variable to only the UDF that is referencing the variable.</span></span> <span data-ttu-id="968eb-122">[UDF 사용 가이드](udf-guide.md)에서는 이러한 상황을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-122">The [guide to using UDFs](udf-guide.md) describes this phenomenon in detail.</span></span> <span data-ttu-id="968eb-123">범위는 브로드캐스트 변수에 대해 `Destroy()`를 호출할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-123">Scope is especially crucial when you call `Destroy()` on the broadcast variable.</span></span>

<span data-ttu-id="968eb-124">제거된 브로드캐스트 변수가 다른 UDF에 표시되거나 다른 UDF에서 액세스 가능한 경우 이 변수를 참조하지 않는 UDF를 포함해 모든 UDF에서 serialization을 위해 이 변수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-124">If the broadcast variable that has been destroyed is visible to or accessible from other UDFs, it gets picked up for serialization by all of the UDFs, even if it is not being referenced by them.</span></span> <span data-ttu-id="968eb-125">.NET for Apache Spark는 제거된 브로드캐스트 변수를 직렬화할 수 없으며 이에 따른 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-125">.NET for Apache Spark is unable to serialize the destroyed broadcast variable, which results in an error.</span></span> <span data-ttu-id="968eb-126">다음 코드 조각은 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-126">The following code snippet demonstrates this error:</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

// Using the broadcast variable in a UDF:
Func<Column, Column> udf1 = Udf<string, string>(
    str => $"{str}: {bv.Value()}");

// Destroying bv
bv.Destroy();

// Calling udf1 after destroying bv throws the following expected exception:
// org.apache.spark.SparkException: Attempted to use Broadcast(0) after it was destroyed
df.Select(udf1(df["_1"])).Show();

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 throws the following (unexpected) exception:
// [Error] [JvmBridge] org.apache.spark.SparkException: Task not serializable
df.Select(udf2(df["_1"])).Show();
```

<span data-ttu-id="968eb-127">다음 코드 조각은 `bv`를 제거해도 예기치 않은 serialization 동작으로 인해 `udf2`에 영향을 주지 않도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-127">The following code snippet demonstrates how to ensure that destroying `bv` doesn't affect `udf2` because of an unexpected serialization behavior:</span></span>

```csharp
string v = "Variable to be broadcasted";
// Restricting the visibility of bv to only the UDF referencing it
{
    Broadcast<string> bv = SparkContext.Broadcast(v);

    // Using the broadcast variable in a UDF:
    Func<Column, Column> udf1 = Udf<string, string>(
        str => $"{str}: {bv.Value()}");

    // Destroying bv
    bv.Destroy();
}

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 works fine as expected
df.Select(udf2(df["_1"])).Show();
```

## <a name="faqs"></a><span data-ttu-id="968eb-128">FAQ</span><span class="sxs-lookup"><span data-stu-id="968eb-128">FAQs</span></span>

<span data-ttu-id="968eb-129">**브로드캐스트 변수가 .NET Interactive에서 작동하지 않는 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="968eb-129">**Why don't Broadcast Variables work with .NET Interactive?**</span></span>  
<span data-ttu-id="968eb-130">브로드캐스트 변수가 대화형 시나리오에서 작동하지 않는 이유는 셀에 정의된 각 개체를 해당 셀 제출 클래스와 함께 추가하는 .NET Interactive의 디자인에 따라 개체가 직렬화 가능으로 표시되지 않으므로 앞서 확인한 것과 동일한 예외가 발생하여 실패하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="968eb-130">Broadcast variables don't work with interactive scenarios because of .NET interactive's design of appending each object defined in a cell with its cell submission class, which since is not marked serializable, fails with the same exception as shown previously.</span></span> <span data-ttu-id="968eb-131">자세한 내용은 [이 문서](dotnet-interactive-udf-issue.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="968eb-131">For more information, please check out [this article](dotnet-interactive-udf-issue.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="968eb-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="968eb-132">Next steps</span></span>

* [<span data-ttu-id="968eb-133">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="968eb-133">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="968eb-134">Windows에서 .NET for Apache Spark 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="968eb-134">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
* [<span data-ttu-id="968eb-135">.NET for Apache Spark 작업자 및 사용자 정의 함수 이진 파일 배포</span><span class="sxs-lookup"><span data-stu-id="968eb-135">Deploy .NET for Apache Spark worker and user-defined function binaries</span></span>](deploy-worker-udf-binaries.md)
