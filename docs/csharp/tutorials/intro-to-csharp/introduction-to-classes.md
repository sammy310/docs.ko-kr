---
title: 클래스 및 개체 - C# 소개 자습서
description: 첫 번째 C# 프로그램을 만들고 개체 지향 개념을 살펴봅니다.
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 3da445e6c656628fffdb9ef9384fb1a1c556a2cd
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255420"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="95224-103">클래스 및 개체를 사용한 개체 지향 프로그래밍 살펴보기</span><span class="sxs-lookup"><span data-stu-id="95224-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="95224-104">이 자습서에서는 콘솔 애플리케이션을 빌드하고 C# 언어의 일부인 기본 개체 지향 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-104">In this tutorial, you'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95224-105">사전 준비 사항</span><span class="sxs-lookup"><span data-stu-id="95224-105">Prerequisites</span></span>

<span data-ttu-id="95224-106">이 자습서에서는 컴퓨터가 로컬 개발용으로 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-106">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="95224-107">Windows, Linux 또는 macOS에서 .NET CLI를 사용하여 애플리케이션을 만들고, 빌드하고, 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-107">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="95224-108">Windows에서 Visual Studio 2019를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-108">On Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="95224-109">설정 지침은 [로컬 환경 설정](../../tour-of-csharp/tutorials/local-environment.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95224-109">For setup instructions, see [Set up your local environment](../../tour-of-csharp/tutorials/local-environment.md).</span></span>

## <a name="create-your-application"></a><span data-ttu-id="95224-110">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="95224-110">Create your application</span></span>

<span data-ttu-id="95224-111">터미널 창을 사용하여 *클래스* 라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-111">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="95224-112">거기에 애플리케이션을 빌드할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-112">You'll build your application there.</span></span> <span data-ttu-id="95224-113">해당 디렉터리로 변경하고 콘솔 창에 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-113">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="95224-114">이 명령은 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-114">This command creates your application.</span></span> <span data-ttu-id="95224-115">*Program.cs* 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="95224-115">Open *Program.cs*.</span></span> <span data-ttu-id="95224-116">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-116">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="95224-117">이 자습서에서는 은행 계좌를 나타내는 새로운 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-117">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="95224-118">일반적으로 개발자는 여러 텍스트 파일에 각 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-118">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="95224-119">그러면 프로그램의 크기가 커질 때 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-119">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="95224-120">*클래스* 디렉터리에 *BankAccount.cs* 라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-120">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="95224-121">이 파일에는 \***은행 계좌** _의 정의가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-121">This file will contain the definition of a \***bank account** _.</span></span> <span data-ttu-id="95224-122">개체 지향 프로그래밍은 클래스 형태로 형식을 생성하여 코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-122">Object Oriented programming organizes code by creating types in the form of _\*_classes_\*\*.</span></span> <span data-ttu-id="95224-123">이러한 클래스에는 특정 엔티티를 나타내는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-123">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="95224-124">`BankAccount` 클래스는 은행 계좌를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95224-124">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="95224-125">코드는 메서드 및 속성을 통해 특정 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-125">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="95224-126">이 자습서에서 은행 계좌는 다음 동작을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-126">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="95224-127">은행 계좌를 고유하게 식별하는 10자리 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-127">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="95224-128">소유자의 이름을 저장하는 문자열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-128">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="95224-129">잔액을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-129">The balance can be retrieved.</span></span>
1. <span data-ttu-id="95224-130">예금을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-130">It accepts deposits.</span></span>
1. <span data-ttu-id="95224-131">인출을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-131">It accepts withdrawals.</span></span>
1. <span data-ttu-id="95224-132">초기 잔액은 양수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-132">The initial balance must be positive.</span></span>
1. <span data-ttu-id="95224-133">인출로 인해 음의 잔액이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-133">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="95224-134">은행 계좌 형식 정의</span><span class="sxs-lookup"><span data-stu-id="95224-134">Define the bank account type</span></span>

<span data-ttu-id="95224-135">동작을 정의하는 클래스의 기본 사항을 만들어 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-135">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="95224-136">**File:New** 명령을 사용하여 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-136">Create a new file using the **File:New** command.</span></span> <span data-ttu-id="95224-137">파일의 이름을 *BankAccount.cs* 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-137">Name it *BankAccount.cs*.</span></span> <span data-ttu-id="95224-138">*BankAccount.cs* 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-138">Add the following code to your *BankAccount.cs* file:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="95224-139">계속하기 전에 빌드한 내용을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-139">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="95224-140">`namespace` 선언은 코드를 논리적으로 구성하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-140">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="95224-141">이 자습서는 비교적 작으므로 하나의 네임스페이스에 모든 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-141">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="95224-142">`public class BankAccount`는 생성하는 클래스 또는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-142">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="95224-143">클래스 선언 뒤에 오는 `{` 및 `}`의 모든 항목은 클래스의 상태와 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-143">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="95224-144">`BankAccount` 클래스의 \***멤버** _가 다섯 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-144">There are five \***members** _ of the `BankAccount` class.</span></span> <span data-ttu-id="95224-145">처음 세 개는 ‘속성’입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-145">The first three are _*_properties_*_.</span></span> <span data-ttu-id="95224-146">속성은 데이터 요소이며 유효성 검사 또는 기타 규칙을 적용하는 코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-146">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="95224-147">마지막 두 개는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-147">The last two are _\*_methods_\*\*.</span></span> <span data-ttu-id="95224-148">메서드는 단일 함수를 수행하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-148">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="95224-149">각 멤버의 이름을 읽으면 사용자 또는 다른 개발자가 클래스가 수행하는 작업을 이해하기에 충분한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-149">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="95224-150">새 계좌 개설</span><span class="sxs-lookup"><span data-stu-id="95224-150">Open a new account</span></span>

<span data-ttu-id="95224-151">구현할 첫 번째 기능은 은행 계좌 개설 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-151">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="95224-152">고객이 계좌를 개설할 때 초기 잔액과 해당 계좌 소유자에 대한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-152">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="95224-153">`BankAccount` 형식의 새 개체를 생성하는 것은 해당 값을 할당하는 **생성자** 를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-153">Creating a new object of the `BankAccount` type means defining a \***constructor** _ that assigns those values.</span></span> <span data-ttu-id="95224-154">생성자는 클래스와 이름이 같은 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-154">A _ *_constructor_*\* is a member that has the same name as the class.</span></span> <span data-ttu-id="95224-155">생성자는 해당 클래스 형식의 개체를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-155">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="95224-156">`BankAccount` 형식에 다음 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-156">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="95224-157">`MakeDeposit` 선언 위에 다음 코드를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-157">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="95224-158">생성자는 [`new`](../../language-reference/operators/new-operator.md)를 사용하여 개체를 만들 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-158">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="95224-159">*Program.cs* 의 `Console.WriteLine("Hello World!");` 줄을 다음 코드로 바꿉니다(`<name>`을 사용자의 이름으로 바꿈).</span><span class="sxs-lookup"><span data-stu-id="95224-159">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="95224-160">지금까지 빌드한 코드를 실행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-160">Let's run what you've built so far.</span></span> <span data-ttu-id="95224-161">Visual Studio를 사용하는 경우 **실행** 메뉴에서 **디버깅하지 않고 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-161">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="95224-162">명령줄을 사용하는 경우 프로젝트를 만든 디렉터리에 `dotnet run`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-162">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="95224-163">계좌 번호가 공백인가요?</span><span class="sxs-lookup"><span data-stu-id="95224-163">Did you notice that the account number is blank?</span></span> <span data-ttu-id="95224-164">이를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-164">It's time to fix that.</span></span> <span data-ttu-id="95224-165">개체가 생성될 때 계좌 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-165">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="95224-166">그러나 계좌 번호 생성은 호출자의 책임이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="95224-166">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="95224-167">`BankAccount` 클래스 코드는 새 계좌 번호를 지정하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-167">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="95224-168">이를 수행하는 간단한 방법은 10자리 숫자로 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-168">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="95224-169">새 계좌가 생성될 때마다 숫자가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="95224-169">Increment it when each new account is created.</span></span> <span data-ttu-id="95224-170">마지막으로, 개체가 생성될 때 현재 계좌 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-170">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="95224-171">`BankAccount` 클래스에 멤버 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-171">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="95224-172">`BankAccount` 클래스의 시작 부분에서 여는 중괄호 `{` 뒤에 다음 코드 줄을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-172">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="95224-173">이는 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-173">This is a data member.</span></span> <span data-ttu-id="95224-174">이것은 `private`입니다. 즉 `BankAccount` 클래스 내의 코드로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-174">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="95224-175">이는 전용 구현(계좌 번호가 생성되는 방법)과 공공 책임(계좌 번호를 가지는 것 등)을 구분하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-175">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="95224-176">모든 `BankAccount` 개체에서 공유됨을 의미하는 `static`이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-176">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="95224-177">비정적 변수의 값은 `BankAccount` 개체의 각 인스턴스에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-177">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="95224-178">생성자에 다음 두 줄을 추가하여 계좌 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-178">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="95224-179">`this.Balance = initialBalance` 줄 뒤에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-179">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="95224-180">`dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-180">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="95224-181">예금 및 인출 만들기</span><span class="sxs-lookup"><span data-stu-id="95224-181">Create deposits and withdrawals</span></span>

<span data-ttu-id="95224-182">은행 계좌 클래스는 제대로 작동하려면 예금과 인출을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-182">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="95224-183">계좌의 모든 트랜잭션에 대한 저널을 만들어 예금과 인출을 구현하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-183">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="95224-184">단순히 각 트랜잭션의 잔액을 업데이트하는 것보다 많은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-184">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="95224-185">기록을 사용하여 모든 트랜잭션을 감사하고 일별 잔액을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-185">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="95224-186">필요한 경우 모든 트랜잭션의 기록에서 잔액을 계산함으로써, 수정된 단일 트랜잭션의 오류가 다음 계산의 잔액에 올바르게 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-186">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="95224-187">트랜잭션을 나타내는 새 형식을 생성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-187">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="95224-188">이는 책임이 없는 단순 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-188">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="95224-189">몇 가지 속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-189">It needs a few properties.</span></span> <span data-ttu-id="95224-190">*Transaction.cs* 라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95224-190">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="95224-191">파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-191">Add the following code to it:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

<span data-ttu-id="95224-192">이제 `Transaction` 개체의 <xref:System.Collections.Generic.List%601>를 `BankAccount` 클래스에 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-192">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="95224-193">*BankAccount.cs* 파일의 생성자 뒤에 다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-193">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

<span data-ttu-id="95224-194"><xref:System.Collections.Generic.List%601> 클래스를 사용하려면 다른 네임스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-194">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="95224-195">*BankAccount.cs* 의 시작 부분에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-195">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="95224-196">이제 `Balance`를 올바르게 계산해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-196">Now, let's correctly compute the `Balance`.</span></span> <span data-ttu-id="95224-197">모든 트랜잭션의 값을 합하여 현재 잔액을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-197">The current balance can be found by summing the values of all transactions.</span></span> <span data-ttu-id="95224-198">코드가 현재 상태이기 때문에 계정의 초기 잔액만 가져올 수 있으므로 `Balance` 속성을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-198">As the code is currently, you can only get the initial balance of the account, so you'll have to update the `Balance` property.</span></span> <span data-ttu-id="95224-199">*BankAccount.cs* 의 `public decimal Balance { get; }` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="95224-199">Replace the line `public decimal Balance { get; }` in *BankAccount.cs* with the following code:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

<span data-ttu-id="95224-200">이 예제에서는 ***속성*** 의 중요한 측면을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95224-200">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="95224-201">이제 다른 프로그래머가 값을 요청할 때 잔액을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-201">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="95224-202">계산은 모든 트랜잭션을 열거하고 합계를 현재 잔액으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-202">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="95224-203">다음으로 `MakeDeposit` 및 `MakeWithdrawal` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-203">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="95224-204">이러한 메서드는 최종 두 규칙을 적용합니다. 초기 잔액은 양수여야 하고 인출로 인해 음수의 잔액이 발생되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-204">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="95224-205">이는 ***예외*** 의 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-205">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="95224-206">메서드가 작업을 성공적으로 완료할 수 없음을 나타내는 일반적인 방법은 예외를 throw하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-206">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="95224-207">예외 형식 및 관련 메시지는 오류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-207">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="95224-208">여기에서 `MakeDeposit` 메서드는 인출 금액이 음수인 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-208">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="95224-209">인출 금액이 음수이거나 인출 적용 후 잔액이 음수인 경우 `MakeWithdrawal` 메서드는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-209">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="95224-210">`allTransactions` 목록의 선언 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-210">Add the following code after the declaration of the `allTransactions` list:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

<span data-ttu-id="95224-211">[`throw`](../../language-reference/keywords/throw.md) 문은 예외를 **throw** 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-211">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="95224-212">현재 블록의 실행이 종료되고 제어가 호출 스택에 있는 처음 일치하는 `catch` 블록으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="95224-212">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="95224-213">`catch` 블록을 추가하여 나중에 이 코드를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-213">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="95224-214">생성자는 잔액을 직접 업데이트하지 않고 초기 트랜잭션을 추가하도록 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-214">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="95224-215">`MakeDeposit` 메서드를 이미 작성했으므로 생성자에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-215">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="95224-216">완성된 생성자는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-216">The finished constructor should look like this:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<span data-ttu-id="95224-217"><xref:System.DateTime.Now?displayProperty=nameWithType>은 현재 날짜 및 시간을 반환하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-217"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="95224-218">새 `BankAccount`를 만드는 코드를 따라 `Main` 메서드에서 몇 가지 예금 및 인출을 추가하여 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-218">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="95224-219">다음으로 음수 잔액을 사용하여 계정을 생성하여 오류 조건을 알아보는 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-219">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="95224-220">방금 추가한 이전 코드 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-220">Add the following code after the preceding code you just added:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="95224-221">[`try` 및 `catch` 문](../../language-reference/keywords/try-catch.md)을 사용하여 예외를 throw할 수 있는 코드 블록을 표시하고 예상한 오류를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-221">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="95224-222">동일한 기술을 사용하여 음수 잔액에 대한 예외를 throw하는 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-222">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="95224-223">`Main` 메서드의 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-223">Add the following code at the end of your `Main` method:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="95224-224">파일을 저장하고 `dotnet run`을 입력하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="95224-224">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="95224-225">과제 - 모든 트랜잭션 기록</span><span class="sxs-lookup"><span data-stu-id="95224-225">Challenge - log all transactions</span></span>

<span data-ttu-id="95224-226">이 자습서를 완료하기 위해 트랜잭션 기록에 대해 `string`을 생성하는 `GetAccountHistory` 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-226">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="95224-227">`BankAccount` 형식에 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-227">Add this method to the `BankAccount` type:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

<span data-ttu-id="95224-228"><xref:System.Text.StringBuilder> 클래스를 사용하여 각 트랜잭션에 대해 한 줄을 포함하는 문자열의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-228">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="95224-229">이러한 자습서의 앞부분에서 문자열 형식 지정 코드를 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-229">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="95224-230">새 문자는 `\t`입니다.</span><span class="sxs-lookup"><span data-stu-id="95224-230">One new character is `\t`.</span></span> <span data-ttu-id="95224-231">이 새 문자는 탭을 삽입하여 출력 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-231">That inserts a tab to format the output.</span></span>

<span data-ttu-id="95224-232">*Program.cs* 에서 테스트하려면 이 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-232">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="95224-233">프로그램을 실행하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95224-233">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95224-234">다음 단계</span><span class="sxs-lookup"><span data-stu-id="95224-234">Next steps</span></span>

<span data-ttu-id="95224-235">잘 알 수 없는 경우 [GitHub 리포지토리](https://github.com/dotnet/docs/tree/main/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes)에서 이 자습서의 소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-235">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/main/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span></span>

<span data-ttu-id="95224-236">[개체 지향 프로그래밍](object-oriented-programming.md) 자습서를 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-236">You can continue with the [object oriented programming](object-oriented-programming.md) tutorial.</span></span>

<span data-ttu-id="95224-237">다음 문서에서 이러한 개념을 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95224-237">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="95224-238">If 및 else 문</span><span class="sxs-lookup"><span data-stu-id="95224-238">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="95224-239">While 문</span><span class="sxs-lookup"><span data-stu-id="95224-239">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="95224-240">Do 문</span><span class="sxs-lookup"><span data-stu-id="95224-240">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="95224-241">For 문</span><span class="sxs-lookup"><span data-stu-id="95224-241">For statement</span></span>](../../language-reference/keywords/for.md)
