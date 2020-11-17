---
title: .NET for Apache Spark 대화형 환경에서 UDF 작성 및 호출
description: .NET for Apache Spark 대화형 셸에서 UDF를 작성하고 호출하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 8fb729a0b8220d15af641f916383bbd6146e2e33
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441078"
---
# <a name="write-and-call-udfs-in-net-for-apache-spark-interactive-environments"></a><span data-ttu-id="2f8fd-103">.NET for Apache Spark 대화형 환경에서 UDF 작성 및 호출</span><span class="sxs-lookup"><span data-stu-id="2f8fd-103">Write and call UDFs in .NET for Apache Spark interactive environments</span></span>

<span data-ttu-id="2f8fd-104">이 문서에서는 .NET for Apache Spark 대화형 환경에서 UDF(사용자 정의 함수)를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-104">In this article, you will learn how to use user-defined functions (UDFs) in a .NET for Apache Spark interactive environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f8fd-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2f8fd-105">Prerequisites</span></span>

1. <span data-ttu-id="2f8fd-106">[.NET Interactive](https://github.com/dotnet/interactive) 설치</span><span class="sxs-lookup"><span data-stu-id="2f8fd-106">Install [.NET Interactive](https://github.com/dotnet/interactive)</span></span>
2. <span data-ttu-id="2f8fd-107">[Jupyter Lab](https://jupyter.org/) 설치</span><span class="sxs-lookup"><span data-stu-id="2f8fd-107">Install [Jupyter lab](https://jupyter.org/)</span></span>

## <a name="net-for-apache-spark-interactive-experience"></a><span data-ttu-id="2f8fd-108">.NET for Apache Spark 대화형 환경</span><span class="sxs-lookup"><span data-stu-id="2f8fd-108">.NET for Apache Spark Interactive experience</span></span>

<span data-ttu-id="2f8fd-109">[.NET for Apache Spark](https://github.com/dotnet/spark)는 [.NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/)를 사용하여 Spark 내의 대화형 환경에 대한 .NET 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-109">[.NET for Apache Spark](https://github.com/dotnet/spark) uses [.NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/) to provide .NET support for interactive experience inside Spark.</span></span> <span data-ttu-id="2f8fd-110">Jupyter Notebook과 함께 .NET Interactive를 사용하도록 환경을 설정하는 방법을 알아보려면 [.NET Interactive 리포지토리](https://github.com/dotnet/interactive)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-110">To understand how to set up the environment to try .NET Interactive with Jupyter notebooks, see the [.NET Interactive repository](https://github.com/dotnet/interactive).</span></span>

<span data-ttu-id="2f8fd-111">또한 [.NET for Apache Spark의 UDF serialization 관련 문서](udf-guide.md)에서 UDF란 무엇인지와 .NET for Apache Spark에서 UDF를 직렬화하는 방법을 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-111">Also, it is recommended to go through [this article about UDF serialization in .NET for Apache Spark](udf-guide.md) to understand what UDFs are and how they are serialized in .NET for Apache Spark.</span></span>
<span data-ttu-id="2f8fd-112">이 가이드에서는 Jupyter Notebook을 이용하여 대화형 환경에서 UDF를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-112">This guide uses Jupyter Notebooks to illustrate how to use UDFs in an interactive experience.</span></span>

## <a name="define-a-udf-in-net-interactive"></a><span data-ttu-id="2f8fd-113">.NET Interactive에서 UDF 정의</span><span class="sxs-lookup"><span data-stu-id="2f8fd-113">Define a UDF in .NET Interactive</span></span>

<span data-ttu-id="2f8fd-114">대화형 환경에서 셀은 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 반복의 일부로 제출되는 코드 조각으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-114">In the interactive experience, a cell can be thought of as the code snippet being submitted as part of one iteration of the [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop).</span></span> <span data-ttu-id="2f8fd-115">예를 들어 그 의미를 이해하기 위해 다음 Notebook을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-115">For example, take a look at the following notebook to understand what that means:</span></span>

![Jupyter Notebook 셀](./media/dotnet-interactive/dotnet-interactive-cells.png)

<span data-ttu-id="2f8fd-117">빨간색 화살표로 표시된 각 블록은 단일 셀이거나 코드를 Spark에 제출하는 단일 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-117">Each of those blocks marked by the red arrow is one cell, or one submission of code to Spark.</span></span> <span data-ttu-id="2f8fd-118">이제 사용자 지정 사용자 정의 개체를 참조하는 UDF를 정의할 때 참조하는 개체가 정의된 셀에서 UDF를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-118">Now when defining a UDF that references a custom user-defined object, it is required that the UDF be defined in the same cell where the object it references is defined.</span></span> <span data-ttu-id="2f8fd-119">예를 들어 다음 코드를 살펴봅시다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-119">Let's look at what that looks like as an example:</span></span>

![제대로 실행되는 UDF](./media/dotnet-interactive/working-udf.png)

## <a name="call-a-udf-on-a-dataframe"></a><span data-ttu-id="2f8fd-121">DataFrame에서 UDF 호출</span><span class="sxs-lookup"><span data-stu-id="2f8fd-121">Call a UDF on a DataFrame</span></span>

<span data-ttu-id="2f8fd-122">이전에 정의한 UDF를 `DataFrame`에서 호출하는 경우 이전 예제와 같이 UDF를 호출하기 전에 UDF가 이전에 제출한 셀에 정의되어 있는지 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-122">When calling a previously defined UDF on a `DataFrame` it is important to make sure the UDF is defined in a previously submitted cell, before calling it, as can be seen in the previous example.</span></span>

<span data-ttu-id="2f8fd-123">이제 UDF가 정의된 셀에서 UDF를 호출하면 어떻게 되는지 살펴봅시다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-123">Now let's see what happens if we call the UDF in the same cell where it is defined.</span></span>

![UDF 호출 실패](./media/dotnet-interactive/udf_fails.png)

<span data-ttu-id="2f8fd-125">위에 강조 표시된 오류는 먼저 UDF 어셈블리를 컴파일하고 작업자에게 제공해야 DataFrame에서 호출할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-125">The above highlighted error is because the UDF assemblies need to first be compiled and shipped to the workers before it can be called on a DataFrame.</span></span>

<span data-ttu-id="2f8fd-126">이상으로 .NET for Apache Spark 대화형 환경(예: [Azure Synapse Notebooks](/azure/synapse-analytics/spark/apache-spark-development-using-notebooks))에서 UDF를 구현하는 동안 유의해야 할 몇 가지 중요한 사항을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-126">These are a few important things to keep in mind while implementing UDFs in .NET for Apache Spark interactive experience (such as [Azure Synapse Notebooks](/azure/synapse-analytics/spark/apache-spark-development-using-notebooks)).</span></span>

## <a name="faqs"></a><span data-ttu-id="2f8fd-127">FAQ</span><span class="sxs-lookup"><span data-stu-id="2f8fd-127">FAQs</span></span>

1. <span data-ttu-id="2f8fd-128">**사용자 지정 사용자 정의 개체를 참조하는 UDF가 `Type Submission#_ is not marked as serializable` 오류를 throw하는 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="2f8fd-128">**Why does my UDF referencing a custom user-defined object throw the error `Type Submission#_ is not marked as serializable`?**</span></span>
    <span data-ttu-id="2f8fd-129">.NET Interactive는 제출되는 각 셀을 고유하게 식별하기 위해 셀 제출 번호의 래퍼 클래스를 사용하여 각 셀을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-129">.NET Interactive wraps each of these cells with a wrapper class of the cell submission number, to uniquely identify each cell being submitted.</span></span> <span data-ttu-id="2f8fd-130">[관련 가이드](udf-guide.md)에 자세히 설명된 것처럼, 사용자 지정 개체를 참조하는 UDF가 직렬화되는 경우 해당 대상도 serialization되도록 선택되므로, .NET Interactive의 경우 사용자 지정 개체가 정의된 셀의 래퍼 클래스로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-130">Now as explained in detail in [this guide](udf-guide.md), when a UDF that references a custom object is being serialized its target is also picked up for serialization, which in the case of .NET Interactive gets wrapped by the wrapper class of the cell where the custom object is defined.</span></span>
    <span data-ttu-id="2f8fd-131">이제 Notebook에서 해당 동작이 UDF 정의에 미치는 영향을 살펴봅시다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-131">Now let's see how that affects our UDF definition in the notebook:</span></span>

    ![UDF serialization 오류](./media/dotnet-interactive/udf-serialization-error.png)

    <span data-ttu-id="2f8fd-133">`udf2_fails`의 경우에서 확인할 수 있듯이, `Submission#7` 유형이 serializable로 표시되지 않는다는 오류 메시지가 나타납니다. 이 오류는 .NET Interactive가 셀에 정의된 모든 개체를 해당 `Submission#` 클래스로 래핑하므로 개체가 즉석에서 생성되어 `Serializable`로 표시되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-133">As can be seen in the case of `udf2_fails`, we see the error message that says Type `Submission#7` is not marked as serializable, this is because .NET Interactive wraps every object defined in a cell with its `Submission#` class, which is generated on the fly and hence is not marked as `Serializable`.</span></span>

    <span data-ttu-id="2f8fd-134">따라서 **사용자 지정 개체를 참조하는 UDF가 해당 개체와 동일한 셀에서 정의되어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-134">For this reason, it is **required that a UDF referencing a custom object is defined in the same cell as that object**.</span></span>

2. <span data-ttu-id="2f8fd-135">**브로드캐스트 변수가 .NET Interactive에서 작동하지 않는 이유는 무엇인가요?**</span><span class="sxs-lookup"><span data-stu-id="2f8fd-135">**Why don't Broadcast Variables work with .NET Interactive?**</span></span>
    <span data-ttu-id="2f8fd-136">앞서 설명한 이유로 브로드캐스트 변수는 .NET Interactive에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-136">For the reasons explained previously, broadcast variables don't work with .NET Interactive.</span></span> <span data-ttu-id="2f8fd-137">[브로드캐스트 변수 관련 가이드](broadcast-guide.md)에서 브로드캐스트 변수란 무엇인지와 브로드캐스트 변수를 사용하는 방법을 자세히 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-137">It is a good idea to go through [this guide on broadcast variables](broadcast-guide.md) to get a deeper understanding of what broadcast variables are and how to use them.</span></span> <span data-ttu-id="2f8fd-138">브로드캐스트 변수가 대화형 시나리오에서 작동하지 않는 이유는 셀에 정의된 각 개체를 해당 셀 제출 클래스와 함께 추가하는 .NET interactive의 디자인에 따라 개체가 serializable로 표시되지 않으므로 앞서 확인한 것과 동일한 예외가 발생하여 실패하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-138">The reason broadcast variables don't work with interactive scenarios is because of .NET interactive's design of appending each object defined in a cell with its cell submission class, which since is not marked serializable, fails with the same exception as shown previously.</span></span>
    <span data-ttu-id="2f8fd-139">다음 예제를 사용하여 좀 더 자세히 살펴봅시다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-139">Let's dive a little deeper with the following example:</span></span>

    ![브로드캐스트 변수 오류](./media/dotnet-interactive/broadcast-fails.png)

    <span data-ttu-id="2f8fd-141">이전 섹션에서 권장한 것처럼 UDF와 UDF가 참조하는 개체(이 예제에서는 브로드캐스트 변수)를 동일한 셀에서 정의하지만 `Microsoft.Spark.Sql.Session`이 serializable로 표시되지 않는다는 `SerializationException` 오류가 여전히 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-141">As recommended in the previous sections, we define both the UDF and the object it is referencing (broadcast variable in this case) in the same cell, but we still see the `SerializationException` error complaining about `Microsoft.Spark.Sql.Session` not being marked as serializable.</span></span> <span data-ttu-id="2f8fd-142">이 오류는 컴파일러가 `bv` 브로드캐스트 변수 개체를 직렬화하려고 할 때 개체 이름이 [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) 개체 `spark`와 함께 추가되므로 serializable로 표시되어야 함을 발견했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-142">This is because when the compiler tries to serialize the broadcast variable object `bv`, it finds its name to be appended with [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) object `spark`, which it requires to be marked as serializable.</span></span> <span data-ttu-id="2f8fd-143">다음 셀 제출의 디컴파일된 어셈블리를 살펴보면 더 쉽게 오류를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-143">This can be demonstrated with more ease by taking a peek at the decompiled assembly of this cell submission:</span></span>

    ![디컴파일된 어셈블리 코드](./media/dotnet-interactive/decompiledAssembly.png)

    <span data-ttu-id="2f8fd-145">[`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) 클래스를 `[Serializable]`로 표시하면 코드가 제대로 실행되지만, SparkSession 개체를 직렬화하는 기능을 사용자에게 제공할 경우 바람직하지 않은 이상한 동작이 생성될 수 있으므로 이상적인 솔루션은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-145">If we mark the [`SparkSession`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) class as `[Serializable]`, we can get this to work, but this is not an ideal solution as we don't want to give the user the ability to serialize a SparkSession object, as that could lead to some weird, undesirable behavior.</span></span> <span data-ttu-id="2f8fd-146">이 오류는 [알려진 문제](https://github.com/dotnet/spark/issues/619)이며, 향후 버전에서 해결될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8fd-146">This is a [known issue](https://github.com/dotnet/spark/issues/619) and will be resolved in future versions.</span></span>
