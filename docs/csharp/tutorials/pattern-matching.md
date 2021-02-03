---
title: '자습서: 패턴 일치를 사용하여 알고리즘 빌드'
description: 이 고급 자습서에서는 패턴 일치 기술을 사용하여 개별적으로 생성된 데이터 및 알고리즘을 사용하여 기능을 만드는 방법을 보여 줍니다.
ms.date: 10/06/2020
ms.technology: csharp-whats-new
ms.custom: contperf-fy21q1
ms.openlocfilehash: be1c330973859df62cd4706e5f6f9ca4326fb221
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794819"
---
# <a name="tutorial-use-pattern-matching-to-build-type-driven-and-data-driven-algorithms"></a><span data-ttu-id="7430d-103">자습서: 패턴 일치를 사용하여 형식 기반 및 데이터 기반 알고리즘 빌드</span><span class="sxs-lookup"><span data-stu-id="7430d-103">Tutorial: Use pattern matching to build type-driven and data-driven algorithms.</span></span>

<span data-ttu-id="7430d-104">C# 7에서는 기본 패턴 일치 기능을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="7430d-105">새로운 식과 패턴을 포함하여 C# 8 및 C# 9에서 기능을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-105">Those features are extended in C# 8 and C# 9 with new expressions and patterns.</span></span> <span data-ttu-id="7430d-106">다른 라이브러리에 있을 수 있는 형식을 확장한 것처럼 동작하는 기능을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="7430d-107">패턴의 또 다른 용도는 확장되는 형식의 기초 기능이 아닌 애플리케이션에 필요한 기능을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="7430d-108">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="7430d-109">패턴 일치를 사용해야 하는 상황을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-109">Recognize situations where pattern matching should be used.</span></span>
> - <span data-ttu-id="7430d-110">패턴 일치 식을 사용하여 형식 및 속성 값에 따라 동작을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> - <span data-ttu-id="7430d-111">패턴 일치를 다른 기술과 결합하여 완전한 알고리즘을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7430d-112">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7430d-112">Prerequisites</span></span>

<span data-ttu-id="7430d-113">C# 9 컴파일러를 포함하는 .NET 5를 실행하도록 머신을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-113">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="7430d-114">C# 9 컴파일러는 [Visual Studio 2019 버전 16.9 미리 보기 1](https://visualstudio.microsoft.com/vs/preview/) 또는 [.NET 5.0 SDK](https://dot.net/get-dotnet5)부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-114">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="7430d-115">이 자습서에서는 Visual Studio 또는 .NET Core CLI를 포함하여 C# 및 .NET에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="7430d-116">패턴 일치 시나리오</span><span class="sxs-lookup"><span data-stu-id="7430d-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="7430d-117">최신 개발에는 종종 여러 소스의 데이터를 통합하고 해당 데이터의 정보와 인사이트를 단일 결합 애플리케이션에서 제공하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="7430d-118">여러분과 팀에는 들어오는 데이터를 나타내는 모든 형식에 대한 제어 또는 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="7430d-119">클래식 개체 지향 디자인의 경우 여러 데이터 소스의 각 데이터 형식을 나타내는 형식을 애플리케이션에서 민들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="7430d-120">그런 다음, 애플리케이션은 이 새로운 형식을 사용하고, 상속 계층 구조를 빌드하고, 가상 메서드를 만들고, 추상화를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="7430d-121">해당 기술이 적용되고 때때로 가장 적합한 도구가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="7430d-122">경우에 따라 더 적은 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-122">Other times you can write less code.</span></span> <span data-ttu-id="7430d-123">데이터를 조작하는 작업에서 데이터를 분리하는 기술을 사용하여 보다 명확한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="7430d-124">이 자습서에서는 단일 시나리오에 대해 여러 외부 소스에서 들어오는 데이터를 사용하는 애플리케이션을 만들고 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="7430d-125">**패턴 일치** 가 원래 시스템에 포함되지 않은 데이터를 사용하고 처리하는 효율적인 방법을 어떻게 제공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="7430d-126">교통량을 관리하는 데 통행료 및 최대 사용 시간 가격을 사용하는 주요 도시 지역을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="7430d-127">형식에 따라 차량의 통행료를 계산하는 애플리케이션을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="7430d-128">나중에 차량 탑승자 수에 따른 가격이 개선 사항에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="7430d-129">추가로 시간 및 요일에 따른 가격이 개선 사항에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="7430d-130">이 간단한 설명을 통해 이 시스템을 모델링하기 위한 개체 계층 구조를 빠르게 설명했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="7430d-131">그러나 데이터는 다른 차량 등록 관리 시스템 같은 다양한 출처에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="7430d-132">이 시스템은 해당 데이터를 모델링하는 여러 가지 클래스를 제공하지만 사용자가 사용할 수 있는 단일 개체 모델이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="7430d-133">이 자습서에서는 다음 코드와 같이 해당 외부 시스템의 차량 데이터를 모델링하는 데 이 간단한 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="7430d-134">시작 코드는 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub 리포지토리에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="7430d-135">차량 클래스는 여러 가지 시스템에서 가져오고 서로 다른 네임스페이스에 포함됨을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="7430d-136">`System.Object` 이외의 공용 기본 클래스는 활용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="7430d-137">패턴 일치 디자인</span><span class="sxs-lookup"><span data-stu-id="7430d-137">Pattern matching designs</span></span>

<span data-ttu-id="7430d-138">이 자습서에서 사용된 시나리오는 패턴 일치를 통해 해결하기에 적합한 종류의 문제를 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well suited to solve:</span></span>

- <span data-ttu-id="7430d-139">사용해야 하는 개체는 목표와 일치하는 개체 계층 구조에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="7430d-140">관련 없는 시스템에 포함된 클래스를 사용 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="7430d-141">추가할 기능은 이 클래스에 대한 핵심 추상화에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="7430d-142">차량에 따른 통행료는 차량 형식에 따라 변경되지만 통행료는 차량의 핵심 기능이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="7430d-143">데이터의 모양과 해당 데이터에 대한 작업을 분리해서 설명하면 C#의 패턴 일치 기능을 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="7430d-144">기본 통행료 계산 구현</span><span class="sxs-lookup"><span data-stu-id="7430d-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="7430d-145">가장 기본적인 통행료 계산에는 차량 형식만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="7430d-146">`Car`는 2.00 USD입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="7430d-147">`Taxi`는 3.50 USD입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="7430d-148">`Bus`는 5.00 USD입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="7430d-149">`DeliveryTruck`은 10.00 USD입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="7430d-150">새 `TollCalculator` 클래스를 만들고 차량 형식에 대한 패턴 일치를 구현하여 통행료 액수를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="7430d-151">다음 코드에서는 `TollCalculator`의 초기 구현을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="7430d-152">앞의 코드는 **형식 패턴** 을 테스트하는 **switch 식**([`switch`](../language-reference/keywords/switch.md) 문과 같지 않음)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="7430d-153">**switch 식** 은 앞의 코드에 있는 `vehicle` 변수로 시작하고 그 뒤에 `switch` 키워드가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="7430d-154">다음은 중괄호로 묶인 모든 **스위치 암(arm)** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="7430d-155">`switch` 식은 `switch` 문을 둘러싸는 구문을 다르게 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="7430d-156">`case` 키워드가 생략되고 각 암(arm)의 결과는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="7430d-157">마지막 두 개의 암(arm)은 새 언어 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="7430d-158">`{ }` 사례는 이전 암(arm)과 일치하지 않는 null이 아닌 개체와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="7430d-159">이 암(arm)은 이 메서드에 전달된 잘못된 형식을 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="7430d-160">`{ }` 사례는 각 차량 형식에 대한 사례를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="7430d-161">순서가 반대로 된 경우 `{ }` 사례가 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="7430d-162">마지막으로 `null`이 이 메서드에 전달될 때 `null` 패턴이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="7430d-163">다른 형식 패턴은 올바른 형식의 null이 아닌 개체와만 일치하므로 `null` 패턴이 마지막일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="7430d-164">`Program.cs`에서 다음 코드를 사용하여 이 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null!);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="7430d-165">해당 코드는 시작 프로젝트에 포함되지만 주석으로 처리됩니다. 주석을 제거하면 작성한 내용을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="7430d-166">먼저 패턴을 사용하여 코드 및 데이터가 구분되는 알고리즘을 만드는 방법을 확인하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="7430d-167">`switch` 식은 형식을 테스트하고 결과에 따라 다른 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="7430d-168">이는 시작에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="7430d-169">점유 가격 추가</span><span class="sxs-lookup"><span data-stu-id="7430d-169">Add occupancy pricing</span></span>

<span data-ttu-id="7430d-170">통행료 징수 기관은 차량이 최대 탑승자 수로 이동하도록 권장하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="7430d-171">차량에 더 적은 승객이 있는 경우 추가 요금을 청구하기로 했으며, 더 낮은 가격을 제공하여 최대 탑승자 차량을 장려합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="7430d-172">승객이 없는 승용차와 택시에는 0.50 USD의 추가 통행료가 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="7430d-173">승객이 2명인 승용차와 택시는 $0.50의 할인을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-173">Cars and taxis with two passengers get a $0.50 discount.</span></span>
- <span data-ttu-id="7430d-174">승객이 3명 이상인 승용차와 택시는 1.00 USD의 할인을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="7430d-175">최대 탑승자 수의 50% 미만이 탑승한 버스는 2.00 USD의 추가 요금이 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="7430d-176">탑승자 수가 90%를 초과하는 버스는 1.00 USD의 할인을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="7430d-177">이 규칙은 동일한 switch 식에서 **속성 패턴** 을 사용하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="7430d-178">속성 패턴은 속성 값을 상수 값과 비교하는 `when` 절입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-178">A property pattern is a `when` clause that compares a property value to a constant value.</span></span> <span data-ttu-id="7430d-179">속성 패턴은 형식이 결정된 후 개체의 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-179">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="7430d-180">`Car` 사례 1개는 다른 사례 4개로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-180">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car {Passengers: 0}        => 2.00m + 0.50m,
    Car {Passengers: 1}        => 2.0m,
    Car {Passengers: 2}        => 2.0m - 0.50m,
    Car c                      => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="7430d-181">처음 3개 사례는 형식을 `Car`로 테스트한 다음, `Passengers` 속성 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-181">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="7430d-182">둘 다 일치하는 경우 해당 식이 계산되고 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-182">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="7430d-183">또한 비슷한 방식으로 택시에 대한 사례를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-183">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi {Fares: 0}  => 3.50m + 1.00m,
    Taxi {Fares: 1}  => 3.50m,
    Taxi {Fares: 2}  => 3.50m - 0.50m,
    Taxi t           => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="7430d-184">앞의 예제에서는 `when` 절이 마지막 사례에서 생략되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-184">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="7430d-185">다음으로, 다음 예제와 같이 버스 사례를 확장하여 점유 규칙을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-185">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="7430d-186">통행료 징수 기관은 배달 트럭의 승객 수에 관심이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-186">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="7430d-187">대신 다음과 같이 트럭의 중량 등급을 기준으로 요금을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-187">Instead, they adjust the toll amount based on the weight class of the trucks as follows:</span></span>

- <span data-ttu-id="7430d-188">5000lbs를 초과하는 트럭에는 5.00 USD가 추가로 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-188">Trucks over 5000 lbs are charged an extra $5.00.</span></span>
- <span data-ttu-id="7430d-189">3000lbs 미만의 경량 트럭에는 $2.00 할인이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-189">Light trucks under 3000 lbs are given a $2.00 discount.</span></span>

<span data-ttu-id="7430d-190">해당 규칙은 다음 코드로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-190">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="7430d-191">앞의 코드는 스위치 암(arm)의 `when` 절을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-191">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="7430d-192">`when` 절을 사용하여 속성에서 같음 이외의 조건을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-192">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="7430d-193">작업을 마치면 다음 코드와 같은 메서드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-193">When you've finished, you'll have a method that looks much like the following code:</span></span>

```csharp
vehicle switch
{
    Car {Passengers: 0}        => 2.00m + 0.50m,
    Car {Passengers: 1}        => 2.0m,
    Car {Passengers: 2}        => 2.0m - 0.50m,
    Car c                      => 2.00m - 1.0m,

    Taxi {Fares: 0}  => 3.50m + 1.00m,
    Taxi {Fares: 1}  => 3.50m,
    Taxi {Fares: 2}  => 3.50m - 0.50m,
    Taxi t           => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,

    { }     => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
    null    => throw new ArgumentNullException(nameof(vehicle))
};
```

<span data-ttu-id="7430d-194">대부분의 이 스위치 암(arm)은 **재귀 패턴** 의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-194">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="7430d-195">예를 들어 `Car { Passengers: 1}`은 속성 패턴 내의 상수 패턴을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-195">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="7430d-196">중첩된 스위치를 사용하여 이 코드의 반복 횟수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-196">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="7430d-197">`Car` 및 `Taxi`에는 둘 다 앞의 예제에 있는 서로 다른 암(arm) 4개가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-197">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="7430d-198">두 경우에 모두 속성 패턴에 제공되는 형식 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-198">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="7430d-199">이 기술이 다음 코드에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-199">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="7430d-200">앞의 샘플에서 재귀 식을 사용하면 속성 값을 테스트하는 자식 암(arm)이 포함된 `Car` 및 `Taxi` 암(arm)을 반복하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-200">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="7430d-201">해당 암(arm)은 불연속 값이 아닌 속성 범위를 테스트하므로 이 기술은 `Bus` 및 `DeliveryTruck` 암(arm)에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-201">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="7430d-202">최대 가격 추가</span><span class="sxs-lookup"><span data-stu-id="7430d-202">Add peak pricing</span></span>

<span data-ttu-id="7430d-203">마지막 기능을 위해 통행료 징수 기관은 시간에 따른 최대 가격을 추가하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-203">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="7430d-204">아침 및 저녁 교통 체증 시간 중에 통행료는 2배로 부과됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-204">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="7430d-205">해당 규칙은 아침에는 도시로 들어오고 저녁 교통 체증 시간에는 나가는 한 방향의 교통량에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-205">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="7430d-206">평일 중 다른 시간에 통행료는 50% 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-206">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="7430d-207">늦은 밤과 이른 아침에는 통행료가 25% 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-207">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="7430d-208">주말에는 시간과 관계없이 정상 요금입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-208">During the weekend, it's the normal rate, regardless of the time.</span></span> <span data-ttu-id="7430d-209">다음 코드를 사용하여 `if` 및 `else` 문으로 표현하는 경우 계열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-209">You could use a series if `if` and `else` statements to express this using the following code:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#SnippetPremiumWithoutPattern)]

<span data-ttu-id="7430d-210">위 코드는 정상적으로 실행되지만 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-210">The preceding code does work correctly, but isn't readable.</span></span> <span data-ttu-id="7430d-211">모든 입력 사례와 중첩된 `if` 문을 연결하여 코드에 대해 추론해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-211">You have to chain through all the input cases and the nested `if` statements to reason about the code.</span></span> <span data-ttu-id="7430d-212">이 기능을 위해 패턴 일치를 대신 사용하되, 다른 기술과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-212">Instead, you'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="7430d-213">방향, 요일 및 시간의 모든 조합을 설명하는 단일 패턴 일치 식을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-213">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="7430d-214">복잡한 식이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-214">The result would be a complicated expression.</span></span> <span data-ttu-id="7430d-215">읽기 힘들고 이해하기 어려운 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-215">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="7430d-216">따라서 식의 정확성을 보장하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-216">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="7430d-217">대신, 해당 메서드를 결합하여 모든 상태를 간결하게 설명하는 값 튜플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-217">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="7430d-218">그런 다음, 패턴 일치를 사용하여 통행료의 승수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-218">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="7430d-219">튜플에는 다음 세 가지 불연속 조건이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-219">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="7430d-220">요일은 주중 또는 주말입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-220">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="7430d-221">통행료가 징수되는 시간대.</span><span class="sxs-lookup"><span data-stu-id="7430d-221">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="7430d-222">방향은 도시 진입 또는 도시 진출입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-222">The direction is into the city or out of the city</span></span>

<span data-ttu-id="7430d-223">다음 표는 입력 값과 최대 가격 승수의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-223">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="7430d-224">일</span><span class="sxs-lookup"><span data-stu-id="7430d-224">Day</span></span>        | <span data-ttu-id="7430d-225">시간</span><span class="sxs-lookup"><span data-stu-id="7430d-225">Time</span></span>         | <span data-ttu-id="7430d-226">Direction</span><span class="sxs-lookup"><span data-stu-id="7430d-226">Direction</span></span> | <span data-ttu-id="7430d-227">Premium</span><span class="sxs-lookup"><span data-stu-id="7430d-227">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="7430d-228">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-228">Weekday</span></span>    | <span data-ttu-id="7430d-229">아침 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-229">morning rush</span></span> | <span data-ttu-id="7430d-230">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-230">inbound</span></span>   | <span data-ttu-id="7430d-231">x 2.00</span><span class="sxs-lookup"><span data-stu-id="7430d-231">x 2.00</span></span>  |
| <span data-ttu-id="7430d-232">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-232">Weekday</span></span>    | <span data-ttu-id="7430d-233">아침 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-233">morning rush</span></span> | <span data-ttu-id="7430d-234">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-234">outbound</span></span>  | <span data-ttu-id="7430d-235">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-235">x 1.00</span></span>  |
| <span data-ttu-id="7430d-236">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-236">Weekday</span></span>    | <span data-ttu-id="7430d-237">주간</span><span class="sxs-lookup"><span data-stu-id="7430d-237">daytime</span></span>      | <span data-ttu-id="7430d-238">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-238">inbound</span></span>   | <span data-ttu-id="7430d-239">x 1.50</span><span class="sxs-lookup"><span data-stu-id="7430d-239">x 1.50</span></span>  |
| <span data-ttu-id="7430d-240">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-240">Weekday</span></span>    | <span data-ttu-id="7430d-241">주간</span><span class="sxs-lookup"><span data-stu-id="7430d-241">daytime</span></span>      | <span data-ttu-id="7430d-242">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-242">outbound</span></span>  | <span data-ttu-id="7430d-243">x 1.50</span><span class="sxs-lookup"><span data-stu-id="7430d-243">x 1.50</span></span>  |
| <span data-ttu-id="7430d-244">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-244">Weekday</span></span>    | <span data-ttu-id="7430d-245">저녁 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-245">evening rush</span></span> | <span data-ttu-id="7430d-246">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-246">inbound</span></span>   | <span data-ttu-id="7430d-247">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-247">x 1.00</span></span>  |
| <span data-ttu-id="7430d-248">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-248">Weekday</span></span>    | <span data-ttu-id="7430d-249">저녁 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-249">evening rush</span></span> | <span data-ttu-id="7430d-250">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-250">outbound</span></span>  | <span data-ttu-id="7430d-251">x 2.00</span><span class="sxs-lookup"><span data-stu-id="7430d-251">x 2.00</span></span>  |
| <span data-ttu-id="7430d-252">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-252">Weekday</span></span>    | <span data-ttu-id="7430d-253">야간</span><span class="sxs-lookup"><span data-stu-id="7430d-253">overnight</span></span>    | <span data-ttu-id="7430d-254">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-254">inbound</span></span>   | <span data-ttu-id="7430d-255">x 0.75</span><span class="sxs-lookup"><span data-stu-id="7430d-255">x 0.75</span></span>  |
| <span data-ttu-id="7430d-256">요일</span><span class="sxs-lookup"><span data-stu-id="7430d-256">Weekday</span></span>    | <span data-ttu-id="7430d-257">야간</span><span class="sxs-lookup"><span data-stu-id="7430d-257">overnight</span></span>    | <span data-ttu-id="7430d-258">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-258">outbound</span></span>  | <span data-ttu-id="7430d-259">x 0.75</span><span class="sxs-lookup"><span data-stu-id="7430d-259">x 0.75</span></span>  |
| <span data-ttu-id="7430d-260">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-260">Weekend</span></span>    | <span data-ttu-id="7430d-261">아침 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-261">morning rush</span></span> | <span data-ttu-id="7430d-262">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-262">inbound</span></span>   | <span data-ttu-id="7430d-263">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-263">x 1.00</span></span>  |
| <span data-ttu-id="7430d-264">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-264">Weekend</span></span>    | <span data-ttu-id="7430d-265">아침 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-265">morning rush</span></span> | <span data-ttu-id="7430d-266">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-266">outbound</span></span>  | <span data-ttu-id="7430d-267">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-267">x 1.00</span></span>  |
| <span data-ttu-id="7430d-268">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-268">Weekend</span></span>    | <span data-ttu-id="7430d-269">주간</span><span class="sxs-lookup"><span data-stu-id="7430d-269">daytime</span></span>      | <span data-ttu-id="7430d-270">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-270">inbound</span></span>   | <span data-ttu-id="7430d-271">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-271">x 1.00</span></span>  |
| <span data-ttu-id="7430d-272">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-272">Weekend</span></span>    | <span data-ttu-id="7430d-273">주간</span><span class="sxs-lookup"><span data-stu-id="7430d-273">daytime</span></span>      | <span data-ttu-id="7430d-274">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-274">outbound</span></span>  | <span data-ttu-id="7430d-275">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-275">x 1.00</span></span>  |
| <span data-ttu-id="7430d-276">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-276">Weekend</span></span>    | <span data-ttu-id="7430d-277">저녁 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-277">evening rush</span></span> | <span data-ttu-id="7430d-278">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-278">inbound</span></span>   | <span data-ttu-id="7430d-279">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-279">x 1.00</span></span>  |
| <span data-ttu-id="7430d-280">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-280">Weekend</span></span>    | <span data-ttu-id="7430d-281">저녁 교통 체증</span><span class="sxs-lookup"><span data-stu-id="7430d-281">evening rush</span></span> | <span data-ttu-id="7430d-282">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-282">outbound</span></span>  | <span data-ttu-id="7430d-283">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-283">x 1.00</span></span>  |
| <span data-ttu-id="7430d-284">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-284">Weekend</span></span>    | <span data-ttu-id="7430d-285">야간</span><span class="sxs-lookup"><span data-stu-id="7430d-285">overnight</span></span>    | <span data-ttu-id="7430d-286">인바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-286">inbound</span></span>   | <span data-ttu-id="7430d-287">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-287">x 1.00</span></span>  |
| <span data-ttu-id="7430d-288">주말</span><span class="sxs-lookup"><span data-stu-id="7430d-288">Weekend</span></span>    | <span data-ttu-id="7430d-289">야간</span><span class="sxs-lookup"><span data-stu-id="7430d-289">overnight</span></span>    | <span data-ttu-id="7430d-290">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="7430d-290">outbound</span></span>  | <span data-ttu-id="7430d-291">x 1.00</span><span class="sxs-lookup"><span data-stu-id="7430d-291">x 1.00</span></span>  |

<span data-ttu-id="7430d-292">세 가지 변수의 조합은 16가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-292">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="7430d-293">일부 조건을 결합하여 마지막 switch 식을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-293">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="7430d-294">통행료를 징수하는 시스템은 통행료가 징수된 시간에 <xref:System.DateTime> 구조체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-294">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="7430d-295">앞의 표에서 변수를 만드는 멤버 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-295">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="7430d-296">다음 함수는 패턴 일치 switch 식을 사용하여 <xref:System.DateTime>이 주말 또는 주중을 나타내는지 여부를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-296">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="7430d-297">해당 메서드는 올바른 것이지만 반복적입니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-297">That method is correct, but it's repetitious.</span></span> <span data-ttu-id="7430d-298">다음 코드와 같이 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-298">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="7430d-299">다음으로, 시간을 블록으로 분류하는 비슷한 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-299">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="7430d-300">프라이빗 `enum`을 추가하여 각 시간 범위를 불연속 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-300">You add a private `enum` to convert each range of time to a discrete value.</span></span> <span data-ttu-id="7430d-301">그러면 `GetTimeBand` 메서드는 ‘관계형 패턴’ 및 ‘or 결합 패턴’을 사용합니다. 두 패턴은 모두 C# 9.0에서 추가된 것입니다. </span><span class="sxs-lookup"><span data-stu-id="7430d-301">Then, the `GetTimeBand` method uses *relational patterns*, and *conjunctive or patterns*, both added in C# 9.0.</span></span> <span data-ttu-id="7430d-302">관계형 패턴을 사용하면 `<`, `>`, `<=` 또는 `>=`로 숫자 값을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-302">The relational pattern lets you test a numeric value using `<`, `>`, `<=`, or `>=`.</span></span> <span data-ttu-id="7430d-303">`or` 패턴은 식이 하나 이상의 패턴과 일치하는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-303">The `or` pattern tests if an expression matches one or more patterns.</span></span> <span data-ttu-id="7430d-304">`and` 패턴을 사용하여 식이 두 개의 고유한 패턴과 일치하는지 확인하고, `not` 패턴을 사용하여 식이 패턴과 일치하지 않는지 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-304">You can also use an `and` pattern to ensure that an expression matches two distinct patterns, and a `not` pattern to test that an expression doesn't match a pattern.</span></span>

<span data-ttu-id="7430d-305">이 메서드를 만든 후 **튜플 패턴** 과 함께 다른 `switch` 식을 사용하여 할증 가격을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-305">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="7430d-306">모든 16개 암(arm)을 사용하여 `switch` 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-306">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="7430d-307">위 코드는 작동하지만 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-307">The above code works, but it can be simplified.</span></span> <span data-ttu-id="7430d-308">주말에 대한 8개 조합에는 모두 동일한 통행료가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-308">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="7430d-309">8개 모두를 다음 줄로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-309">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="7430d-310">인바운드 및 아웃바운드 교통량은 둘 다 주중 주간 및 야간 시간 동안 동일한 승수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-310">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="7430d-311">해당하는 4개의 스위치 암(arm)은 다음 두 줄로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-311">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="7430d-312">해당하는 두 줄이 변경된 후 코드는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-312">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="7430d-313">마지막으로 정규 가격을 납부하는 두 번의 교통 체증 시간을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-313">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="7430d-314">해당 암(arm)을 제거하면 마지막 스위치 암(arm)에서 `false`를 삭제(`_`)로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-314">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="7430d-315">완료된 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-315">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="7430d-316">이 예제는 패턴 일치의 장점 중 하나를 강조 표시합니다. 패턴 분기는 순서대로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-316">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="7430d-317">이전 분기가 이후 사례 중 하나를 처리하도록 분기를 재배열하는 경우 컴파일러는 접근할 수 없는 코드에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-317">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="7430d-318">이 언어 규칙을 사용하면 코드가 변경되지 않는다는 확신과 함께 앞의 단순화 작업을 더 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-318">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="7430d-319">패턴 일치는 일부 유형의 코드를 더 쉽게 읽을 수 있도록 해주며 클래스에 코드를 추가할 수 없을 때 개체 지향 기술에 대한 대안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-319">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="7430d-320">클라우드에서는 데이터와 기능이 별도로 구분되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-320">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="7430d-321">데이터의 모양과 데이터에 대한 작업을 반드시 함께 설명할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-321">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="7430d-322">이 자습서에서는 원래 함수와 완전히 다른 방식으로 기존 데이터를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-322">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="7430d-323">해당 형식을 확장할 수 없더라도 패턴 일치를 통해 해당 형식을 재정의하는 기능을 작성할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-323">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7430d-324">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7430d-324">Next steps</span></span>

<span data-ttu-id="7430d-325">완료된 코드는 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub 리포지토리에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-325">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="7430d-326">혼자 패턴을 살펴보고 이 기술을 일반적인 코딩 활동에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="7430d-326">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="7430d-327">이 기술을 학습하면 다른 방법으로 문제에 접근하고 새 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7430d-327">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
