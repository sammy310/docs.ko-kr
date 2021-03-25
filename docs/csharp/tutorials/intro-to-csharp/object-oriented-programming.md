---
title: 개체 지향 프로그래밍(C#)
description: C#은 추상화, 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대한 모든 지원을 제공합니다.
ms.date: 09/30/2020
ms.openlocfilehash: e6261e9018217094e0c3ce742ff0172b8559deaf
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624216"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="234d0-103">개체 지향 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="234d0-103">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="234d0-104">C#는 개체 지향 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-104">C# is an object-oriented language.</span></span> <span data-ttu-id="234d0-105">개체 지향 프로그래밍에 사용되는 네 가지 주요 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-105">Four of the key techniques used in object-oriented programming are:</span></span>

- <span data-ttu-id="234d0-106">‘추상화’는 관련된 속성, 메서드, 기타 멤버의 그룹을 단일 단위나 개체로 처리하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-106">*Abstraction* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="234d0-107">‘캡슐화’는 형식 소비자의 불필요한 세부 정보를 숨기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-107">*Encapsulation* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="234d0-108">*상속* 은 기존 클래스를 기반으로 새로운 클래스를 만들 수 있는 능력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-108">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="234d0-109">*다형성* 은 동일한 속성 또는 메서드를 각각 다른 방식으로 구현하는 여러 클래스를 서로 교체하여 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-109">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="234d0-110">앞의 [클래스 소개](introduction-to-classes.md) 자습서에서 추상화와 캡슐화를 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-110">In the preceding tutorial, [introduction to classes](introduction-to-classes.md) you saw both *abstraction* and *encapsulation*.</span></span> <span data-ttu-id="234d0-111">`BankAccount` 클래스는 은행 계좌 개념에 대한 추상화를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-111">The `BankAccount` class provided an abstraction for the concept of a bank account.</span></span> <span data-ttu-id="234d0-112">`BankAccount` 클래스를 사용한 코드에 영향을 주지 않고 해당 구현을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-112">You could modify its implementation without affecting any of the code that used the `BankAccount` class.</span></span> <span data-ttu-id="234d0-113">`BankAccount` 및 `Transaction` 클래스는 코드에서 이러한 개념을 설명하는 데 필요한 구성 요소의 캡슐화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-113">Both the `BankAccount` and `Transaction` classes provide encapsulation of the components needed to describe those concepts in code.</span></span>

<span data-ttu-id="234d0-114">이 자습서에서는 상속과 다형성을 활용하도록 이 애플리케이션을 확장해 새 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-114">In this tutorial, you'll extend that application to make use of *inheritance* and *polymorphism* to add new features.</span></span> <span data-ttu-id="234d0-115">또한 `BankAccount` 클래스에 기능을 추가하여 앞의 자습서에서 배운 추상화 및 캡슐화 방법을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-115">You'll also add features to the `BankAccount` class, taking advantage of the *abstraction* and *encapsulation* techniques you learned in the preceding tutorial.</span></span>

## <a name="create-different-types-of-accounts"></a><span data-ttu-id="234d0-116">다른 유형의 계좌 만들기</span><span class="sxs-lookup"><span data-stu-id="234d0-116">Create different types of accounts</span></span>

<span data-ttu-id="234d0-117">이 프로그램을 빌드한 후 기능 추가를 요청 받습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-117">After building this program, you get requests to add features to it.</span></span> <span data-ttu-id="234d0-118">이 프로그램은 은행 계좌 유형이 하나뿐인 상황에서는 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-118">It works great in the situation where there is only one bank account type.</span></span> <span data-ttu-id="234d0-119">시간이 지나면서 요구 사항이 바뀌고 관련된 다음과 같은 계정 유형이 요청됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-119">Over time, needs change, and related account types are requested:</span></span>

- <span data-ttu-id="234d0-120">매월말에 이자가 붙는 이자 소득 계좌.</span><span class="sxs-lookup"><span data-stu-id="234d0-120">An interest earning account that accrues interest at the end of each month.</span></span>
- <span data-ttu-id="234d0-121">잔고가 음수일 수 있지만 잔고가 있는 경우 매달 이자 비용이 발생하는 신용 한도.</span><span class="sxs-lookup"><span data-stu-id="234d0-121">A line of credit that can have a negative balance, but when there's a balance, there's an interest charge each month.</span></span>
- <span data-ttu-id="234d0-122">1회 예치로 시작하고 지불만 가능한 선불 선물 카드 계좌.</span><span class="sxs-lookup"><span data-stu-id="234d0-122">A pre-paid gift card account that starts with a single deposit, and only can be paid off.</span></span> <span data-ttu-id="234d0-123">이 계좌는 매월초에 한 번 잔고를 다시 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-123">It can be refilled once at the start of each month.</span></span>

<span data-ttu-id="234d0-124">이 모든 다양한 계좌는 이전 자습서에서 정의한 `BankAccount` 클래스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-124">All of these different accounts are similar to `BankAccount` class defined in the earlier tutorial.</span></span> <span data-ttu-id="234d0-125">해당 코드를 복사하고 클래스 이름을 바꾸고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-125">You could copy that code, rename the classes, and make modifications.</span></span> <span data-ttu-id="234d0-126">이 방법은 단기적으로는 효과가 있지만 시간이 지남에 따라 작업이 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-126">That technique would work in the short term, but it would be more work over time.</span></span> <span data-ttu-id="234d0-127">모든 변경 내용은 영향을 받는 모든 클래스에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-127">Any changes would be copied across all the affected classes.</span></span>

<span data-ttu-id="234d0-128">대신 이전 자습서에서 만든 `BankAccount` 클래스에서 메서드와 데이터를 상속하는 새 은행 계좌 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-128">Instead, you can create new bank account types that inherit methods and data from the `BankAccount` class created in the preceding tutorial.</span></span> <span data-ttu-id="234d0-129">이러한 새 클래스는 각 유형에 필요한 특정 동작으로 `BankAccount` 클래스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-129">These new classes can extend the `BankAccount` class with the specific behavior needed for each type:</span></span>

```csharp
public class InterestEarningAccount : BankAccount
{
}

public class LineOfCreditAccount : BankAccount
{
}

public class GiftCardAccount : BankAccount
{
}
```

<span data-ttu-id="234d0-130">이러한 각 클래스는 공유 기본 클래스인 `BankAccount` 클래스에서 공유 동작을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-130">Each of these classes *inherits* the shared behavior from their shared *base class*, the `BankAccount` class.</span></span> <span data-ttu-id="234d0-131">파생 클래스 각각에 새롭고 다양한 기능의 구현을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-131">Write the implementations for new and different functionality in each of the *derived classes*.</span></span>  <span data-ttu-id="234d0-132">이러한 파생 클래스에는 이미 `BankAccount` 클래스에 정의된 동작이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-132">These derived classes already have all the behavior defined in the `BankAccount` class.</span></span>

<span data-ttu-id="234d0-133">각각의 새 클래스는 서로 다른 소스 파일에 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-133">It's a good practice to create each new class in a different source file.</span></span> <span data-ttu-id="234d0-134">[Visual Studio](https://visualstudio.com)에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 클래스 추가를 선택하여 새 파일에 새 클래스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-134">In [Visual Studio](https://visualstudio.com), you can right-click on the project, and select *add class* to add a new class in a new file.</span></span> <span data-ttu-id="234d0-135">[Visual Studio Code](https://code.visualstudio.com)에서는 파일을 선택한 다음 새로 만들기를 선택하여 새 원본 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-135">In [Visual Studio Code](https://code.visualstudio.com), select *File* then *New* to create a new source file.</span></span> <span data-ttu-id="234d0-136">어느 도구에서나 클래스와 일치하도록 파일 이름을 지정합니다. *InterestEarningAccount.cs*, *LineOfCreditAccount.cs*, *GiftCardAccount.cs*.</span><span class="sxs-lookup"><span data-stu-id="234d0-136">In either tool, name the file to match the class: *InterestEarningAccount.cs*, *LineOfCreditAccount.cs*, and *GiftCardAccount.cs*.</span></span>

<span data-ttu-id="234d0-137">위의 샘플에 나온 것처럼 클래스를 만들면 파생 클래스가 컴파일되지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-137">When you create the classes as shown in the preceding sample, you'll find that none of your derived classes compile.</span></span> <span data-ttu-id="234d0-138">생성자는 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-138">A constructor is responsible for initializing an object.</span></span> <span data-ttu-id="234d0-139">파생 클래스 생성자는 파생 클래스를 초기화하고 파생 클래스에 포함된 기본 클래스 개체를 초기화하는 방법에 대한 지침을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-139">A derived class constructor must initialize the derived class, and provide instructions on how to initialize the base class object included in the derived class.</span></span> <span data-ttu-id="234d0-140">적절한 초기화는 일반적으로 추가 코드 없이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-140">The proper initialization normally happens without any extra code.</span></span> <span data-ttu-id="234d0-141">`BankAccount` 클래스는 다음 서명을 사용하여 하나의 공용 생성자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-141">The `BankAccount` class declares one public constructor with the following signature:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
```

<span data-ttu-id="234d0-142">컴파일러는 사용자가 직접 생성자를 정의할 때 기본 생성자를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-142">The compiler doesn't generate a default constructor when you define a constructor yourself.</span></span> <span data-ttu-id="234d0-143">즉, 각 파생 클래스가 이 생성자를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-143">That means each derived class must explicitly call this constructor.</span></span> <span data-ttu-id="234d0-144">기본 클래스 생성자에 인수를 전달할 수 있는 생성자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-144">You declare a constructor that can pass arguments to the base class constructor.</span></span>  <span data-ttu-id="234d0-145">다음 코드는 `InterestEarningAccount`의 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-145">The following code shows the constructor for the `InterestEarningAccount`:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="DerivedConstructor":::

<span data-ttu-id="234d0-146">이 새로운 생성자의 매개 변수는 기본 클래스 생성자의 매개 변수 형식 및 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-146">The parameters to this new constructor match the parameter type and names of the base class constructor.</span></span> <span data-ttu-id="234d0-147">`: base()` 구문을 사용하여 기본 클래스 생성자에 대한 호출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-147">You use the `: base()` syntax to indicate a call to a base class constructor.</span></span> <span data-ttu-id="234d0-148">일부 클래스는 여러 생성자를 정의하며, 이 구문을 사용하면 호출하는 기본 클래스 생성자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-148">Some classes define multiple constructors, and this syntax enables you to pick which base class constructor you call.</span></span> <span data-ttu-id="234d0-149">생성자를 업데이트한 후 각 파생 클래스의 코드를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-149">Once you've updated the constructors, you can develop the code for each of the derived classes.</span></span> <span data-ttu-id="234d0-150">새 클래스에 대한 요구 사항은 다음과 같이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-150">The requirements for the new classes can be stated as follows:</span></span>

- <span data-ttu-id="234d0-151">이자 소득 계좌:</span><span class="sxs-lookup"><span data-stu-id="234d0-151">An interest earning account:</span></span>
  - <span data-ttu-id="234d0-152">월말 잔고의 2%에 해당하는 예금을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-152">Will get a credit of 2% of the month-ending-balance.</span></span>
- <span data-ttu-id="234d0-153">신용 한도:</span><span class="sxs-lookup"><span data-stu-id="234d0-153">A line of credit:</span></span>
  - <span data-ttu-id="234d0-154">음수의 잔고일 수 있지만 절대값은 대출 한도보다 클 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-154">Can have a negative balance, but not be greater in absolute value than the credit limit.</span></span>
  - <span data-ttu-id="234d0-155">월말 잔고가 0이 아닌 경우 매달 이자 비용이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-155">Will incur an interest charge each month where the end of month balance isn't 0.</span></span>
  - <span data-ttu-id="234d0-156">대출 한도를 초과하는 인출 때마다 수수료가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-156">Will incur a fee on each withdrawal that goes over the credit limit.</span></span>
- <span data-ttu-id="234d0-157">선물 카드 계좌:</span><span class="sxs-lookup"><span data-stu-id="234d0-157">A gift card account:</span></span>
  - <span data-ttu-id="234d0-158">매월 한 번 말일에 지정된 금액으로 계좌를 다시 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-158">Can be refilled with a specified amount once each month, on the last day of the month.</span></span>

<span data-ttu-id="234d0-159">이러한 계좌 유형 세 가지 모두 월말에 발생하는 작업이 있음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-159">You can see that all three of these account types have an action that takes places at the end of each month.</span></span> <span data-ttu-id="234d0-160">하지만 계좌 유형마다 수행하는 작업은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-160">However, each account type does different tasks.</span></span> <span data-ttu-id="234d0-161">다형성을 사용하여 이 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-161">You use *polymorphism* to implement this code.</span></span> <span data-ttu-id="234d0-162">`BankAccount` 클래스에서 단일 `virtual` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-162">Create a single `virtual` method in the `BankAccount` class:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="DeclareMonthEndTransactions":::

<span data-ttu-id="234d0-163">앞의 코드는 `virtual` 키워드를 사용하여 파생 클래스가 다른 구현을 제공할 수 있는 기본 클래스에서 메서드를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-163">The preceding code shows how you use the `virtual` keyword to declare a method in the base class that a derived class may provide a different implementation for.</span></span> <span data-ttu-id="234d0-164">`virtual` 메서드는 파생 클래스가 다시 구현하도록 선택할 수 있는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-164">A `virtual` method is a method where any derived class may choose to reimplement.</span></span> <span data-ttu-id="234d0-165">파생 클래스는 `override` 키워드를 사용하여 새 구현을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-165">The derived classes use the `override` keyword to define the new implementation.</span></span> <span data-ttu-id="234d0-166">일반적으로 이것을 “기본 클래스 구현 재정의”라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-166">Typically you refer to this as "overriding the base class implementation".</span></span> <span data-ttu-id="234d0-167">`virtual` 키워드는 파생 클래스가 동작을 재정의할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-167">The `virtual` keyword specifies that derived classes may override the behavior.</span></span> <span data-ttu-id="234d0-168">파생 클래스가 동작을 재정의해야 하는 `abstract` 메서드를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-168">You can also declare `abstract` methods where derived classes must override the behavior.</span></span> <span data-ttu-id="234d0-169">기본 클래스는 `abstract` 메서드의 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-169">The base class does not provide an implementation for an `abstract` method.</span></span> <span data-ttu-id="234d0-170">다음으로 만든 새로운 두 클래스의 구현을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-170">Next, you need to define the implementation for two of the new classes you've created.</span></span> <span data-ttu-id="234d0-171">`InterestEarningAccount`로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-171">Start with the `InterestEarningAccount`:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="ApplyMonthendInterest":::

<span data-ttu-id="234d0-172">`LineOfCreditAccount`에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-172">Add the following code to the `LineOfCreditAccount`.</span></span> <span data-ttu-id="234d0-173">이 코드는 계좌에서 인출되는 양수의 이자 비용을 계산하기 위해 잔고를 무효화합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-173">The code negates the balance to compute a positive interest charge that is withdrawn from the account:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ApplyMonthendInterest":::

<span data-ttu-id="234d0-174">`GiftCardAccount` 클래스가 해당 월말 기능을 구현하려면 두 가지 변경이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-174">The `GiftCardAccount` class needs two changes to implement its month-end functionality.</span></span> <span data-ttu-id="234d0-175">먼저 매월 더할 선택적 금액을 포함하도록 생성자를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-175">First, modify the constructor to include an optional amount to add each month:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="GiftCardAccountConstruction":::

<span data-ttu-id="234d0-176">생성자는 `monthlyDeposit` 값의 기본값을 제공하므로 호출자는 월별 예치금이 없는 `0`을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-176">The constructor provides a default value for the `monthlyDeposit` value so callers can omit a `0` for no monthly deposit.</span></span> <span data-ttu-id="234d0-177">다음으로 생성자에서 0이 아닌 값으로 설정된 경우 월별 예치금을 추가하도록 `PerformMonthEndTransactions` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-177">Next, override the `PerformMonthEndTransactions` method to add the monthly deposit, if it was set to a non-zero value in the constructor:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="AddMonthlyDeposit":::

<span data-ttu-id="234d0-178">재정의는 생성자에서 설정된 월별 예치금을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-178">The override applies the monthly deposit set in the constructor.</span></span> <span data-ttu-id="234d0-179">`Main` 메서드에 다음 코드를 추가하여 `GiftCardAccount` 및 `InterestEarningAccount`에 대한 이러한 변경을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-179">Add the following code to the `Main` method to test these changes for the `GiftCardAccount` and the `InterestEarningAccount`:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="FirstTests":::

<span data-ttu-id="234d0-180">결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-180">Verify the results.</span></span> <span data-ttu-id="234d0-181">이제 `LineOfCreditAccount`에 대한 유사한 테스트 코드 집합을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-181">Now, add a similar set of test code for the `LineOfCreditAccount`:</span></span>

```
    var lineOfCredit = new LineOfCreditAccount("line of credit", 0);
    // How much is too much to borrow?
    lineOfCredit.MakeWithdrawal(1000m, DateTime.Now, "Take out monthly advance");
    lineOfCredit.MakeDeposit(50m, DateTime.Now, "Pay back small amount");
    lineOfCredit.MakeWithdrawal(5000m, DateTime.Now, "Emergency funds for repairs");
    lineOfCredit.MakeDeposit(150m, DateTime.Now, "Partial restoration on repairs");
    lineOfCredit.PerformMonthEndTransactions();
    Console.WriteLine(lineOfCredit.GetAccountHistory());
 ```

<span data-ttu-id="234d0-182">앞의 코드를 추가하고 프로그램을 실행하면 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-182">When you add the preceding code and run the program, you'll see something like the following error:</span></span>

```console
Unhandled exception. System.ArgumentOutOfRangeException: Amount of deposit must be positive (Parameter 'amount')
   at OOProgramming.BankAccount.MakeDeposit(Decimal amount, DateTime date, String note) in BankAccount.cs:line 42
   at OOProgramming.BankAccount..ctor(String name, Decimal initialBalance) in BankAccount.cs:line 31
   at OOProgramming.LineOfCreditAccount..ctor(String name, Decimal initialBalance) in LineOfCreditAccount.cs:line 9
   at OOProgramming.Program.Main(String[] args) in Program.cs:line 29
```

> [!NOTE]
> <span data-ttu-id="234d0-183">실제 출력에는 프로젝트와 함께 폴더의 전체 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-183">The actual output includes the full path to the folder with the project.</span></span> <span data-ttu-id="234d0-184">간단히 하기 위해 폴더 이름이 생략되었습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-184">The folder names were omitted for brevity.</span></span> <span data-ttu-id="234d0-185">또한 코드 형식에 따라 줄 번호가 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-185">Also, depending on your code format, the line numbers may be slightly different.</span></span>

<span data-ttu-id="234d0-186">`BankAccount`는 초기 잔고가 0보다 커야 한다고 가정하기 때문에 이 코드는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-186">This code fails because the `BankAccount` assumes that the initial balance must be greater than 0.</span></span> <span data-ttu-id="234d0-187">`BankAccount` 클래스에 베이킹된 또 다른 가정은 잔고는 음수가 될 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-187">Another assumption baked into the `BankAccount` class is that the balance can't go negative.</span></span> <span data-ttu-id="234d0-188">대신 계좌 잔고를 초과하는 인출은 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-188">Instead, any withdrawal that overdraws the account is rejected.</span></span> <span data-ttu-id="234d0-189">두 가지 가정 모두 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-189">Both of those assumptions need to change.</span></span> <span data-ttu-id="234d0-190">신용 한도 계좌는 0에서 시작하며, 일반적으로 음수의 잔고를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-190">The line of credit account starts at 0, and generally will have a negative balance.</span></span> <span data-ttu-id="234d0-191">또한 고객이 너무 많은 비용을 빌리는 경우 수수료가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-191">Also, if a customer borrows too much money, they incur a fee.</span></span> <span data-ttu-id="234d0-192">트랜잭션은 허용되지만 비용이 더 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-192">The transaction is accepted, it just costs more.</span></span> <span data-ttu-id="234d0-193">첫 번째 규칙은 최소 잔고를 지정하는 `BankAccount` 생성자에 선택적 인수를 추가하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-193">The first rule can be implemented by adding an optional argument to the `BankAccount` constructor that specifies the minimum balance.</span></span> <span data-ttu-id="234d0-194">기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-194">The default is `0`.</span></span> <span data-ttu-id="234d0-195">두 번째 규칙에는 파생 클래스가 기본 알고리즘을 수정할 수 있도록 하는 메커니즘이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-195">The second rule requires a mechanism that enables derived classes to modify the default algorithm.</span></span> <span data-ttu-id="234d0-196">어떤 면에서 기본 클래스는 초과 인출이 있을 때 수행해야 하는 작업을 파생 형식에게 ‘물어봅니다’.</span><span class="sxs-lookup"><span data-stu-id="234d0-196">In a sense, the base class "asks" the derived type what should happen when there's an overdraft.</span></span> <span data-ttu-id="234d0-197">기본 동작은 예외를 throw하여 트랜잭션을 거부하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-197">The default behavior is to reject the transaction by throwing an exception.</span></span>

<span data-ttu-id="234d0-198">선택적 `minimumBalance` 매개 변수를 포함하는 두 번째 생성자를 추가하여 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-198">Let's start by adding a second constructor that includes an optional `minimumBalance` parameter.</span></span> <span data-ttu-id="234d0-199">이 새 생성자는 기존 생성자가 수행하는 모든 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-199">This new constructor does all the actions done by the existing constructor.</span></span> <span data-ttu-id="234d0-200">또한 최소 잔고 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-200">Also, it sets the minimum balance property.</span></span> <span data-ttu-id="234d0-201">기존 생성자의 본문을 복사할 수도 있지만</span><span class="sxs-lookup"><span data-stu-id="234d0-201">You could copy the body of the existing constructor.</span></span> <span data-ttu-id="234d0-202">그러면 나중에 두 위치를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-202">but that means two locations to change in the future.</span></span> <span data-ttu-id="234d0-203">대신 생성자 연결을 사용하여 한 생성자가 다른 생성자를 호출하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-203">Instead, you can use *constructor chaining* to have one constructor call another.</span></span> <span data-ttu-id="234d0-204">다음 코드는 두 개의 생성자와 새 추가 필드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-204">The following code shows the two constructors and the new additional field:</span></span>

 :::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="ConstructorModifications":::

<span data-ttu-id="234d0-205">앞의 코드는 두 가지 새로운 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-205">The preceding code shows two new techniques.</span></span> <span data-ttu-id="234d0-206">첫째, `minimumBalance` 필드는 `readonly`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-206">First, the `minimumBalance` field is marked as `readonly`.</span></span> <span data-ttu-id="234d0-207">즉, 개체가 생성된 후에는 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-207">That means the value cannot be changed after the object is constructed.</span></span> <span data-ttu-id="234d0-208">`BankAccount`가 만들어지면 `minimumBalance`를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-208">Once a `BankAccount` is created, the `minimumBalance` can't change.</span></span> <span data-ttu-id="234d0-209">둘째, 두 매개 변수를 취하는 생성자는 `: this(name, initialBalance, 0) { }`를 구현으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-209">Second, the constructor that takes two parameters uses `: this(name, initialBalance, 0) { }` as its implementation.</span></span> <span data-ttu-id="234d0-210">`: this()` 식은 매개 변수가 세 개인 다른 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-210">The `: this()` expression calls the other constructor, the one with three parameters.</span></span> <span data-ttu-id="234d0-211">이 방법을 사용하면 클라이언트 코드가 여러 생성자 중 하나를 선택할 수 있더라도 개체 초기화에 단일 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-211">This technique allows you to have a single implementation for initializing an object even though client code can choose one of many constructors.</span></span>

<span data-ttu-id="234d0-212">이 구현은 초기 잔고가 `0`보다 큰 경우에만 `MakeDeposit`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-212">This implementation calls `MakeDeposit` only if the initial balance is greater than `0`.</span></span> <span data-ttu-id="234d0-213">그러면 예치금은 양수여야 한다는 규칙이 유지되지만 신용 계정이 `0`의 잔고로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-213">That preserves the rule that deposits must be positive, yet lets the credit account open with a `0` balance.</span></span>

<span data-ttu-id="234d0-214">이제 `BankAccount` 클래스에 최소 잔고에 대한 읽기 전용 필드가 있으므로 마지막 변경은 `MakeWithdrawal` 메서드에서 하드 코드를 `0`에서 `minimumBalance`로 변경하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-214">Now that the `BankAccount` class has a read-only field for the minimum balance, the final change is to change the hard code `0` to `minimumBalance` in the `MakeWithdrawal` method:</span></span>

```csharp
if (Balance - amount < minimumBalance)
```

<span data-ttu-id="234d0-215">`BankAccount` 클래스를 확장한 후 다음 코드에 나온 것처럼 새 기본 생성자를 호출하도록 `LineOfCreditAccount` 생성자를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-215">After extending the `BankAccount` class, you can modify the `LineOfCreditAccount` constructor to call the new base constructor, as shown in the following code:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ConstructLineOfCredit":::

<span data-ttu-id="234d0-216">`LineOfCreditAccount` 생성자는 `minimumBalance` 매개 변수의 의미와 일치하도록 `creditLimit` 매개 변수의 부호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-216">Notice that the `LineOfCreditAccount` constructor changes the sign of the `creditLimit` parameter so it matches the meaning of the `minimumBalance` parameter.</span></span>

## <a name="different-overdraft-rules"></a><span data-ttu-id="234d0-217">다른 초과 인출 규칙</span><span class="sxs-lookup"><span data-stu-id="234d0-217">Different overdraft rules</span></span>

<span data-ttu-id="234d0-218">추가할 마지막 기능을 사용하면 `LineOfCreditAccount`는 트랜잭션을 거부하는 대신 대출 한도 초과에 대해 수수료를 청구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-218">The last feature to add enables the `LineOfCreditAccount` to charge a fee for going over the credit limit instead of refusing the transaction.</span></span>

<span data-ttu-id="234d0-219">한 가지 방법은 필요한 동작을 구현하는 가상 함수를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-219">One technique is to define a virtual function where you implement the required behavior.</span></span> <span data-ttu-id="234d0-220">`BankAccount` 클래스는 `MakeWithdrawal` 메서드를 두 개의 메서드로 리팩터링합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-220">The `BankAccount` class refactors the `MakeWithdrawal` method into two methods.</span></span> <span data-ttu-id="234d0-221">새 메서드는 인출로 잔고가 최솟값보다 낮아지면 지정된 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-221">The new method does the specified action when the withdrawal takes the balance below the minimum.</span></span> <span data-ttu-id="234d0-222">기존 `MakeWithdrawal` 메서드에는 다음과 같은 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-222">The existing `MakeWithdrawal` method has the following code:</span></span>

```csharp
public void MakeWithdrawal(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of withdrawal must be positive");
    }
    if (Balance - amount < minimumBalance)
    {
        throw new InvalidOperationException("Not sufficient funds for this withdrawal");
    }
    var withdrawal = new Transaction(-amount, date, note);
    allTransactions.Add(withdrawal);
}
```

<span data-ttu-id="234d0-223">다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-223">Replace it with the following code:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="RefactoredMakeWithdrawal":::

<span data-ttu-id="234d0-224">추가된 메서드는 `protected`로, 파생 클래스에서만 호출할 수 있음을 뜻합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-224">The added method is `protected`, which means that it can be called only from derived classes.</span></span> <span data-ttu-id="234d0-225">이렇게 선언하면 다른 클라이언트가 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-225">That declaration prevents other clients from calling the method.</span></span> <span data-ttu-id="234d0-226">또한 파생 클래스가 동작을 변경할 수 있도록 `virtual`입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-226">It's also `virtual` so that derived classes can change the behavior.</span></span> <span data-ttu-id="234d0-227">반환 형식은 `Transaction?`입니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-227">The return type is a `Transaction?`.</span></span> <span data-ttu-id="234d0-228">`?` 주석은 메서드가 `null`을 반환할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-228">The `?` annotation indicates that the method may return `null`.</span></span> <span data-ttu-id="234d0-229">인출 한도를 초과할 때 수수료를 청구하기 위해 `LineOfCreditAccount`에 다음 구현을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-229">Add the following implementation in the `LineOfCreditAccount` to charge a fee when the withdrawal limit is exceeded:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="AddOverdraftFee":::

<span data-ttu-id="234d0-230">재정의는 계좌에서 초과 인출할 때 수수료 트랜잭션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-230">The override returns a fee transaction when the account is overdrawn.</span></span> <span data-ttu-id="234d0-231">인출이 한도를 초과하지 않으면 메서드는 `null` 트랜잭션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-231">If the withdrawal doesn't go over the limit, the method returns a `null` transaction.</span></span> <span data-ttu-id="234d0-232">이는 수수료가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-232">That indicates there's no fee.</span></span> <span data-ttu-id="234d0-233">`Program` 클래스의 `Main` 메서드에 다음 코드를 추가하여 이러한 변경 내용을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-233">Test these changes by adding the following code to your `Main` method in the `Program` class:</span></span>

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

<span data-ttu-id="234d0-234">프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-234">Run the program, and check the results.</span></span>

## <a name="summary"></a><span data-ttu-id="234d0-235">요약</span><span class="sxs-lookup"><span data-stu-id="234d0-235">Summary</span></span>

<span data-ttu-id="234d0-236">잘 알 수 없는 경우 [GitHub 리포지토리](https://github.com/dotnet/docs/tree/main/docs/csharp/tutorials/intro-to-csharp/snippets/object-oriented-programming)에서 이 자습서의 소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-236">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/main/docs/csharp/tutorials/intro-to-csharp/snippets/object-oriented-programming).</span></span>

<span data-ttu-id="234d0-237">이 자습서에서 개체 지향 프로그래밍에 사용되는 다양한 방법을 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-237">This tutorial demonstrated many of the techniques used in Object-Oriented programming:</span></span>

- <span data-ttu-id="234d0-238">각 계좌 유형의 클래스를 정의할 때 추상화를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-238">You used *Abstraction* when you defined classes for each of the different account types.</span></span> <span data-ttu-id="234d0-239">이러한 클래스는 해당 계좌 유형의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-239">Those classes described the behavior for that type of account.</span></span>
- <span data-ttu-id="234d0-240">각 클래스에서 많은 세부 정보를 `private`으로 유지하는 경우 캡슐화를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-240">You used *Encapsulation* when you kept many details `private` in each class.</span></span>
- <span data-ttu-id="234d0-241">`BankAccount` 클래스에서 이미 만든 구현을 활용하여 코드를 저장하는 경우 상속을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-241">You used *Inheritance* when you leveraged the implementation already created in the `BankAccount` class to save code.</span></span>
- <span data-ttu-id="234d0-242">파생 클래스가 해당 계좌 유형의 특정 동작을 만들기 위해 재정의할 수 있는 `virtual` 메서드를 만들 때 다형성을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-242">You used *Polymorphism* when you created `virtual` methods that derived classes could override to create specific behavior for that account type.</span></span>

<span data-ttu-id="234d0-243">축하합니다. 모든 C# 소개 자습서를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="234d0-243">Congratulations, you've finished all of our introduction to C# tutorials.</span></span> <span data-ttu-id="234d0-244">더 자세한 내용은 추가 [자습서](../index.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="234d0-244">To learn more, try more of our [tutorials](../index.md).</span></span>
