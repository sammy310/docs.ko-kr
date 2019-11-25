---
title: 클래스 및 개체 - C# 소개 자습서
description: 첫 번째 C# 프로그램을 만들고 개체 지향 개념을 살펴봅니다.
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: e4cf7912de69946289c0594944b8ac3a8c252ac2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736835"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="de216-103">클래스 및 개체를 사용한 개체 지향 프로그래밍 살펴보기</span><span class="sxs-lookup"><span data-stu-id="de216-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="de216-104">이 자습서에서는 개발에 사용할 수 있는 머신이 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="de216-105">.NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)에는 Windows, Linux 또는 macOS의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="de216-106">사용할 명령에 대한 간단한 개요는 [개발 도구 익히기](local-environment.md)에 자세한 정보의 링크와 함께 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="de216-107">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="de216-107">Create your application</span></span>

<span data-ttu-id="de216-108">터미널 창을 사용하여 *클래스*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de216-108">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="de216-109">거기에 애플리케이션을 빌드할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-109">You'll build your application there.</span></span> <span data-ttu-id="de216-110">해당 디렉터리로 변경하고 콘솔 창에 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="de216-111">이 명령은 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de216-111">This command creates your application.</span></span> <span data-ttu-id="de216-112">*Program.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="de216-112">Open *Program.cs*.</span></span> <span data-ttu-id="de216-113">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-113">It should look like this:</span></span>

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

<span data-ttu-id="de216-114">이 자습서에서는 은행 계좌를 나타내는 새로운 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de216-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="de216-115">일반적으로 개발자는 여러 텍스트 파일에 각 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="de216-116">그러면 프로그램의 크기가 커질 때 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="de216-117">*클래스* 디렉터리에 *BankAccount.cs*라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de216-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span> 

<span data-ttu-id="de216-118">이 파일에는 ***은행 계좌***의 정의가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="de216-119">개체 지향 프로그래밍은 ***클래스*** 형태로 형식을 생성하여 코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="de216-120">이러한 클래스에는 특정 엔티티를 나타내는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="de216-121">`BankAccount` 클래스는 은행 계좌를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de216-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="de216-122">코드는 메서드 및 속성을 통해 특정 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="de216-123">이 자습서에서 은행 계좌는 다음 동작을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="de216-124">은행 계좌를 고유하게 식별하는 10자리 숫자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="de216-125">소유자의 이름을 저장하는 문자열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="de216-126">잔액을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="de216-127">예금을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-127">It accepts deposits.</span></span>
1. <span data-ttu-id="de216-128">인출을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="de216-129">초기 잔액은 양수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="de216-130">인출로 인해 음의 잔액이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="de216-131">은행 계좌 형식 정의</span><span class="sxs-lookup"><span data-stu-id="de216-131">Define the bank account type</span></span>

<span data-ttu-id="de216-132">동작을 정의하는 클래스의 기본 사항을 만들어 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="de216-133">다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-133">It would look like this:</span></span>

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

<span data-ttu-id="de216-134">계속하기 전에 빌드한 내용을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="de216-135">`namespace` 선언은 코드를 논리적으로 구성하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="de216-136">이 자습서는 비교적 작으므로 하나의 네임스페이스에 모든 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="de216-137">`public class BankAccount`는 생성하는 클래스 또는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="de216-138">클래스 선언 뒤에 오는 `{` 및 `}`의 모든 항목은 클래스의 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="de216-139">`BankAccount` 클래스의 ***멤버***가 다섯 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="de216-140">첫 번째 세 개는 ***속성***입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-140">The first three are ***properties***.</span></span> <span data-ttu-id="de216-141">속성은 데이터 요소이며 유효성 검사 또는 기타 규칙을 적용하는 코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="de216-142">마지막 두 개는 ***메서드***입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-142">The last two are ***methods***.</span></span> <span data-ttu-id="de216-143">메서드는 단일 함수를 수행하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="de216-144">각 멤버의 이름을 읽으면 사용자 또는 다른 개발자가 클래스가 수행하는 작업을 이해하기에 충분한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="de216-145">새 계좌 개설</span><span class="sxs-lookup"><span data-stu-id="de216-145">Open a new account</span></span>

<span data-ttu-id="de216-146">구현할 첫 번째 기능은 은행 계좌 개설 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="de216-147">고객이 계좌를 개설할 때 초기 잔액과 해당 계좌 소유자에 대한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="de216-148">`BankAccount` 형식의 새 개체를 생성하는 것은 해당 값을 지정하는 ***생성자***를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="de216-149">***생성자***는 클래스와 이름이 같은 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="de216-150">생성자는 해당 클래스 형식의 개체를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="de216-151">`BankAccount` 형식에 다음 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="de216-152">생성자는 [`new`](../../language-reference/operators/new-operator.md)를 사용하여 개체를 만들 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-152">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="de216-153">*Program.cs*의 `Console.WriteLine("Hello World!");` 줄을 다음 줄로 바꿉니다(`<name>`을 사용자의 이름으로 바꿈).</span><span class="sxs-lookup"><span data-stu-id="de216-153">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="de216-154">`dotnet run`을 입력하고 어떤 일이 일어나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="de216-155">계좌 번호가 공백인가요?</span><span class="sxs-lookup"><span data-stu-id="de216-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="de216-156">이를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-156">It's time to fix that.</span></span> <span data-ttu-id="de216-157">개체가 생성될 때 계좌 번호를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="de216-158">그러나 계좌 번호 생성은 호출자의 책임이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="de216-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="de216-159">`BankAccount` 클래스 코드는 새 계좌 번호를 지정하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="de216-160">이를 수행하는 간단한 방법은 10자리 숫자로 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="de216-161">새 계좌가 생성될 때마다 숫자가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="de216-161">Increment it when each new account is created.</span></span> <span data-ttu-id="de216-162">마지막으로, 개체가 생성될 때 현재 계좌 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="de216-163">`BankAccount` 클래스에 다음 멤버 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="de216-164">이는 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-164">This is a data member.</span></span> <span data-ttu-id="de216-165">이것은 `private`입니다. 즉 `BankAccount` 클래스 내의 코드로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="de216-166">이는 전용 구현(계좌 번호가 생성되는 방법)과 공공 책임(계좌 번호를 가지는 것 등)을 구분하는 방법입니다. 모든 `BankAccount` 개체에서 공유됨을 의미하는 `static`이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="de216-167">비정적 변수의 값은 `BankAccount` 개체의 각 인스턴스에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-167">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="de216-168">생성자에 다음 두 줄을 추가하여 계좌 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-168">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="de216-169">`dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-169">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="de216-170">예금 및 인출 만들기</span><span class="sxs-lookup"><span data-stu-id="de216-170">Create deposits and withdrawals</span></span>

<span data-ttu-id="de216-171">은행 계좌 클래스는 제대로 작동하려면 예금과 인출을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-171">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="de216-172">계좌의 모든 트랜잭션에 대한 저널을 만들어 예금과 인출을 구현하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-172">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="de216-173">단순히 각 트랜잭션의 잔액을 업데이트하는 것보다 많은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-173">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="de216-174">기록을 사용하여 모든 트랜잭션을 감사하고 일별 잔액을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-174">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="de216-175">필요한 경우 모든 트랜잭션의 기록에서 잔액을 계산함으로써, 수정된 단일 트랜잭션의 오류가 다음 계산의 잔액에 올바르게 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-175">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="de216-176">트랜잭션을 나타내는 새 형식을 생성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-176">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="de216-177">이는 책임이 없는 단순 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-177">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="de216-178">몇 가지 속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-178">It needs a few properties.</span></span> <span data-ttu-id="de216-179">*Transaction.cs*라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="de216-179">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="de216-180">파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-180">Add the following code to it:</span></span>

[!code-csharp[Transaction](~/samples/csharp/classes-quickstart/Transaction.cs)]

<span data-ttu-id="de216-181">이제 `Transaction` 개체의 <xref:System.Collections.Generic.List%601>를 `BankAccount` 클래스에 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-181">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="de216-182">다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-182">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](~/samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration)]

<span data-ttu-id="de216-183"><xref:System.Collections.Generic.List%601> 클래스를 사용하려면 다른 네임스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-183">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="de216-184">*BankAccount.cs*의 시작 부분에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-184">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="de216-185">이제 `Balance`를 보고하는 방법을 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-185">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="de216-186">모든 트랜잭션의 값을 합하여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-186">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="de216-187">`BankAccount` 클래스에서 `Balance`의 선언을 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-187">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](~/samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation)]

<span data-ttu-id="de216-188">이 예제에서는 ***속성***의 중요한 측면을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de216-188">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="de216-189">이제 다른 프로그래머가 값을 요청할 때 잔액을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-189">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="de216-190">계산은 모든 트랜잭션을 열거하고 합계를 현재 잔액으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-190">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="de216-191">다음으로 `MakeDeposit` 및 `MakeWithdrawal` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-191">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="de216-192">이러한 메서드는 최종 두 규칙을 적용합니다. 초기 잔액은 양수여야 하고 인출로 인해 음수의 잔액이 발생되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-192">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="de216-193">이는 ***예외***의 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-193">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="de216-194">메서드가 작업을 성공적으로 완료할 수 없음을 나타내는 일반적인 방법은 예외를 throw하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-194">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="de216-195">예외 형식 및 관련 메시지는 오류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-195">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="de216-196">여기에서 `MakeDeposit` 메서드는 인출 금액이 음수인 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-196">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="de216-197">인출 금액이 음수이거나 인출 적용 결과로 음수의 잔액이 발생하는 경우 `MakeWithdrawal` 메서드는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-197">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](~/samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal)]

<span data-ttu-id="de216-198">[`throw`](../../language-reference/keywords/throw.md) 문은 예외를 **throw**합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-198">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="de216-199">현재 블록의 실행이 종료되고 제어가 호출 스택에 있는 처음 일치하는 `catch` 블록으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="de216-199">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="de216-200">`catch` 블록을 추가하여 나중에 이 코드를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-200">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="de216-201">생성자는 잔액을 직접 업데이트하지 않고 초기 트랜잭션을 추가하도록 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-201">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="de216-202">`MakeDeposit` 메서드를 이미 작성했으므로 생성자에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-202">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="de216-203">완성된 생성자는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-203">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](~/samples/csharp/classes-quickstart/BankAccount.cs#Constructor)]

<span data-ttu-id="de216-204"><xref:System.DateTime.Now?displayProperty=nameWithType>은 현재 날짜 및 시간을 반환하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-204"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="de216-205">`Main` 메서드에 예금 및 인출을 몇 개 추가하여 다음을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-205">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="de216-206">다음으로 음수 잔액을 사용하여 계정을 생성하여 오류 조건을 알아보는 테스트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-206">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

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

<span data-ttu-id="de216-207">[`try` 및 `catch` 문](../../language-reference/keywords/try-catch.md)을 사용하여 예외를 throw할 수 있는 코드 블록을 표시하고 예상한 오류를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-207">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="de216-208">동일한 기술을 사용하여 음수 잔액에 대한 예외를 throw하는 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-208">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

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

<span data-ttu-id="de216-209">파일을 저장하고 `dotnet run`을 입력하여 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="de216-209">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="de216-210">과제 - 모든 트랜잭션 기록</span><span class="sxs-lookup"><span data-stu-id="de216-210">Challenge - log all transactions</span></span>

<span data-ttu-id="de216-211">이 자습서를 완료하기 위해 트랜잭션 기록에 대해 `string`을 생성하는 `GetAccountHistory` 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-211">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="de216-212">`BankAccount` 형식에 이 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-212">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](~/samples/csharp/classes-quickstart/BankAccount.cs#History)]

<span data-ttu-id="de216-213"><xref:System.Text.StringBuilder> 클래스를 사용하여 각 트랜잭션에 대해 한 줄을 포함하는 문자열의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-213">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="de216-214">이러한 자습서의 앞부분에서 문자열 형식 지정 코드를 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-214">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="de216-215">새 문자는 `\t`입니다.</span><span class="sxs-lookup"><span data-stu-id="de216-215">One new character is `\t`.</span></span> <span data-ttu-id="de216-216">이 새 문자는 탭을 삽입하여 출력 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-216">That inserts a tab to format the output.</span></span>

<span data-ttu-id="de216-217">*Program.cs*에서 테스트하려면 이 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-217">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="de216-218">`dotnet run`을 입력하여 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de216-218">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de216-219">다음 단계</span><span class="sxs-lookup"><span data-stu-id="de216-219">Next steps</span></span>

<span data-ttu-id="de216-220">잘 알 수 없는 경우 [GitHub 리포지토리](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)에서 이 자습서의 소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-220">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/).</span></span>

<span data-ttu-id="de216-221">축하합니다. 모든 C# 소개 자습서를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="de216-221">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="de216-222">더 자세히 학습하려면 추가 [자습서](../index.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="de216-222">If you're eager to learn more, try more of our [tutorials](../index.md).</span></span>
