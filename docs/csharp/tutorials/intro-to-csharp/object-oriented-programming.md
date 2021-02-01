---
title: 개체 지향 프로그래밍(C#)
description: C#은 추상화, 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대한 모든 지원을 제공합니다.
ms.date: 09/30/2020
ms.openlocfilehash: b778b7c42bbfb1f20bdd2d83b9cb10512ea3f41b
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794843"
---
# <a name="object-oriented-programming-c"></a>개체 지향 프로그래밍(C#)

C#는 개체 지향 언어입니다. 개체 지향 프로그래밍에 사용되는 네 가지 주요 방법은 다음과 같습니다.

- ‘추상화’는 형식 소비자의 불필요한 세부 정보를 숨기는 것입니다.
- *캡슐화* 는 서로 관련된 속성, 메서드 및 기타 멤버의 그룹을 하나의 단위나 개체로 취급하는 것을 말합니다.
- *상속* 은 기존 클래스를 기반으로 새로운 클래스를 만들 수 있는 능력을 나타냅니다.
- *다형성* 은 동일한 속성 또는 메서드를 각각 다른 방식으로 구현하는 여러 클래스를 서로 교체하여 사용할 수 있음을 의미합니다.

앞의 [클래스 소개](introduction-to-classes.md) 자습서에서 추상화와 캡슐화를 살펴봤습니다. `BankAccount` 클래스는 은행 계좌 개념에 대한 추상화를 제공했습니다. `BankAccount` 클래스를 사용한 코드에 영향을 주지 않고 해당 구현을 수정할 수 있습니다. `BankAccount` 및 `Transaction` 클래스는 코드에서 이러한 개념을 설명하는 데 필요한 구성 요소의 캡슐화를 제공합니다.

이 자습서에서는 상속과 다형성을 활용하도록 이 애플리케이션을 확장해 새 기능을 추가합니다. 또한 `BankAccount` 클래스에 기능을 추가하여 앞의 자습서에서 배운 추상화 및 캡슐화 방법을 활용합니다.

## <a name="create-different-types-of-accounts"></a>다른 유형의 계좌 만들기

이 프로그램을 빌드한 후 기능 추가를 요청 받습니다. 이 프로그램은 은행 계좌 유형이 하나뿐인 상황에서는 잘 작동합니다. 시간이 지나면서 요구 사항이 바뀌고 관련된 다음과 같은 계정 유형이 요청됩니다.

- 매월말에 이자가 붙는 이자 소득 계좌.
- 잔고가 음수일 수 있지만 잔고가 있는 경우 매달 이자 비용이 발생하는 신용 한도.
- 1회 예치로 시작하고 지불만 가능한 선불 선물 카드 계좌. 이 계좌는 매월초에 한 번 잔고를 다시 채울 수 있습니다.

이 모든 다양한 계좌는 이전 자습서에서 정의한 `BankAccount` 클래스와 비슷합니다. 해당 코드를 복사하고 클래스 이름을 바꾸고 수정할 수도 있습니다. 이 방법은 단기적으로는 효과가 있지만 시간이 지남에 따라 작업이 늘어납니다. 모든 변경 내용은 영향을 받는 모든 클래스에 복사됩니다.

대신 이전 자습서에서 만든 `BankAccount` 클래스에서 메서드와 데이터를 상속하는 새 은행 계좌 유형을 만들 수 있습니다. 이러한 새 클래스는 각 유형에 필요한 특정 동작으로 `BankAccount` 클래스를 확장할 수 있습니다.

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

이러한 각 클래스는 공유 기본 클래스인 `BankAccount` 클래스에서 공유 동작을 상속합니다. 파생 클래스 각각에 새롭고 다양한 기능의 구현을 작성합니다.  이러한 파생 클래스에는 이미 `BankAccount` 클래스에 정의된 동작이 모두 있습니다.

각각의 새 클래스는 서로 다른 소스 파일에 만드는 것이 좋습니다. [Visual Studio](https://visualstudio.com)에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 클래스 추가를 선택하여 새 파일에 새 클래스를 추가할 수 있습니다. [Visual Studio Code](https://code.visualstudio.com)에서는 파일을 선택한 다음 새로 만들기를 선택하여 새 원본 파일을 만듭니다. 어느 도구에서나 클래스와 일치하도록 파일 이름을 지정합니다. *InterestEarningAccount.cs*, *LineOfCreditAccount.cs*, *GiftCardAccount.cs*.

위의 샘플에 나온 것처럼 클래스를 만들면 파생 클래스가 컴파일되지 않는 것을 확인할 수 있습니다. 생성자는 개체를 초기화합니다. 파생 클래스 생성자는 파생 클래스를 초기화하고 파생 클래스에 포함된 기본 클래스 개체를 초기화하는 방법에 대한 지침을 제공해야 합니다. 적절한 초기화는 일반적으로 추가 코드 없이 발생합니다. `BankAccount` 클래스는 다음 서명을 사용하여 하나의 공용 생성자를 선언합니다.

```csharp
public BankAccount(string name, decimal initialBalance)
```

컴파일러는 사용자가 직접 생성자를 정의할 때 기본 생성자를 생성하지 않습니다. 즉, 각 파생 클래스가 이 생성자를 명시적으로 호출해야 합니다. 기본 클래스 생성자에 인수를 전달할 수 있는 생성자를 선언합니다.  다음 코드는 `InterestEarningAccount`의 생성자를 보여 줍니다.

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="DerivedConstructor":::

이 새로운 생성자의 매개 변수는 기본 클래스 생성자의 매개 변수 형식 및 이름과 일치합니다. `: base()` 구문을 사용하여 기본 클래스 생성자에 대한 호출을 나타낼 수 있습니다. 일부 클래스는 여러 생성자를 정의하며, 이 구문을 사용하면 호출하는 기본 클래스 생성자를 선택할 수 있습니다. 생성자를 업데이트한 후 각 파생 클래스의 코드를 개발할 수 있습니다. 새 클래스에 대한 요구 사항은 다음과 같이 지정할 수 있습니다.

- 이자 소득 계좌:
  - 월말 잔고의 2%에 해당하는 예금을 얻게 됩니다.
- 신용 한도:
  - 음수의 잔고일 수 있지만 절대값은 대출 한도보다 클 수 없습니다.
  - 월말 잔고가 0이 아닌 경우 매달 이자 비용이 발생합니다.
  - 대출 한도를 초과하는 인출 때마다 수수료가 발생합니다.
- 선물 카드 계좌:
  - 매월 한 번 말일에 지정된 금액으로 계좌를 다시 채울 수 있습니다.

이러한 계좌 유형 세 가지 모두 월말에 발생하는 작업이 있음을 볼 수 있습니다. 하지만 계좌 유형마다 수행하는 작업은 다릅니다. 다형성을 사용하여 이 코드를 구현합니다. `BankAccount` 클래스에서 단일 `virtual` 메서드를 만듭니다.

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="DeclareMonthEndTransactions":::

앞의 코드는 `virtual` 키워드를 사용하여 파생 클래스가 다른 구현을 제공할 수 있는 기본 클래스에서 메서드를 선언하는 방법을 보여 줍니다. `virtual` 메서드는 파생 클래스가 다시 구현하도록 선택할 수 있는 메서드입니다. 파생 클래스는 `override` 키워드를 사용하여 새 구현을 정의합니다. 일반적으로 이것을 “기본 클래스 구현 재정의”라고 합니다. `virtual` 키워드는 파생 클래스가 동작을 재정의할 수 있도록 지정합니다. 파생 클래스가 동작을 재정의해야 하는 `abstract` 메서드를 선언할 수도 있습니다. 기본 클래스는 `abstract` 메서드의 구현을 제공하지 않습니다. 다음으로 만든 새로운 두 클래스의 구현을 정의해야 합니다. `InterestEarningAccount`로 시작합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="ApplyMonthendInterest":::

`LineOfCreditAccount`에 다음 코드를 추가합니다. 이 코드는 계좌에서 인출되는 양수의 이자 비용을 계산하기 위해 잔고를 무효화합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ApplyMonthendInterest":::

`GiftCardAccount` 클래스가 해당 월말 기능을 구현하려면 두 가지 변경이 필요합니다. 먼저 매월 더할 선택적 금액을 포함하도록 생성자를 수정합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="GiftCardAccountConstruction":::

생성자는 `monthlyDeposit` 값의 기본값을 제공하므로 호출자는 월별 예치금이 없는 `0`을 생략할 수 있습니다. 다음으로 생성자에서 0이 아닌 값으로 설정된 경우 월별 예치금을 추가하도록 `PerformMonthEndTransactions` 메서드를 재정의합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="AddMonthlyDeposit":::

재정의는 생성자에서 설정된 월별 예치금을 적용합니다. `Main` 메서드에 다음 코드를 추가하여 `GiftCardAccount` 및 `InterestEarningAccount`에 대한 이러한 변경을 테스트합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="FirstTests":::

결과를 확인합니다. 이제 `LineOfCreditAccount`에 대한 유사한 테스트 코드 집합을 추가합니다.

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

앞의 코드를 추가하고 프로그램을 실행하면 다음과 같은 오류가 표시됩니다.

```console
Unhandled exception. System.ArgumentOutOfRangeException: Amount of deposit must be positive (Parameter 'amount')
   at OOProgramming.BankAccount.MakeDeposit(Decimal amount, DateTime date, String note) in BankAccount.cs:line 42
   at OOProgramming.BankAccount..ctor(String name, Decimal initialBalance) in BankAccount.cs:line 31
   at OOProgramming.LineOfCreditAccount..ctor(String name, Decimal initialBalance) in LineOfCreditAccount.cs:line 9
   at OOProgramming.Program.Main(String[] args) in Program.cs:line 29
```

> [!NOTE]
> 실제 출력에는 프로젝트와 함께 폴더의 전체 경로가 포함됩니다. 간단히 하기 위해 폴더 이름이 생략되었습니다. 또한 코드 형식에 따라 줄 번호가 약간 다를 수 있습니다.

`BankAccount`는 초기 잔고가 0보다 커야 한다고 가정하기 때문에 이 코드는 실패합니다. `BankAccount` 클래스에 베이킹된 또 다른 가정은 잔고는 음수가 될 수 없다는 것입니다. 대신 계좌 잔고를 초과하는 인출은 거부됩니다. 두 가지 가정 모두 변경해야 합니다. 신용 한도 계좌는 0에서 시작하며, 일반적으로 음수의 잔고를 갖습니다. 또한 고객이 너무 많은 비용을 빌리는 경우 수수료가 발생합니다. 트랜잭션은 허용되지만 비용이 더 많이 듭니다. 첫 번째 규칙은 최소 잔고를 지정하는 `BankAccount` 생성자에 선택적 인수를 추가하여 구현할 수 있습니다. 기본값은 `0`입니다. 두 번째 규칙에는 파생 클래스가 기본 알고리즘을 수정할 수 있도록 하는 메커니즘이 필요합니다. 어떤 면에서 기본 클래스는 초과 인출이 있을 때 수행해야 하는 작업을 파생 형식에게 ‘물어봅니다’. 기본 동작은 예외를 throw하여 트랜잭션을 거부하는 것입니다.

선택적 `minimumBalance` 매개 변수를 포함하는 두 번째 생성자를 추가하여 시작해 보겠습니다. 이 새 생성자는 기존 생성자가 수행하는 모든 작업을 수행합니다. 또한 최소 잔고 속성을 설정합니다. 기존 생성자의 본문을 복사할 수도 있지만 그러면 나중에 두 위치를 변경해야 합니다. 대신 생성자 연결을 사용하여 한 생성자가 다른 생성자를 호출하도록 할 수 있습니다. 다음 코드는 두 개의 생성자와 새 추가 필드를 보여 줍니다.

 :::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="ConstructorModifications":::

앞의 코드는 두 가지 새로운 방법을 보여 줍니다. 첫째, `minimumBalance` 필드는 `readonly`로 표시됩니다. 즉, 개체가 생성된 후에는 값을 변경할 수 없습니다. `BankAccount`가 만들어지면 `minimumBalance`를 변경할 수 없습니다. 둘째, 두 매개 변수를 취하는 생성자는 `: this(name, initialBalance, 0) { }`를 구현으로 사용합니다. `: this()` 식은 매개 변수가 세 개인 다른 생성자를 호출합니다. 이 방법을 사용하면 클라이언트 코드가 여러 생성자 중 하나를 선택할 수 있더라도 개체 초기화에 단일 구현을 사용할 수 있습니다.

이 구현은 초기 잔고가 `0`보다 큰 경우에만 `MakeDeposit`을 호출합니다. 그러면 예치금은 양수여야 한다는 규칙이 유지되지만 신용 계정이 `0`의 잔고로 열립니다.

이제 `BankAccount` 클래스에 최소 잔고에 대한 읽기 전용 필드가 있으므로 마지막 변경은 `MakeWithdrawal` 메서드에서 하드 코드를 `0`에서 `minimumBalance`로 변경하는 것입니다.

```csharp
if (Balance - amount < minimumBalance)
```

`BankAccount` 클래스를 확장한 후 다음 코드에 나온 것처럼 새 기본 생성자를 호출하도록 `LineOfCreditAccount` 생성자를 수정할 수 있습니다.

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ConstructLineOfCredit":::

`LineOfCreditAccount` 생성자는 `minimumBalance` 매개 변수의 의미와 일치하도록 `creditLimit` 매개 변수의 부호를 변경할 수 있습니다.

## <a name="different-overdraft-rules"></a>다른 초과 인출 규칙

추가할 마지막 기능을 사용하면 `LineOfCreditAccount`는 트랜잭션을 거부하는 대신 대출 한도 초과에 대해 수수료를 청구할 수 있습니다.

한 가지 방법은 필요한 동작을 구현하는 가상 함수를 정의하는 것입니다. `BankAccount` 클래스는 `MakeWithdrawal` 메서드를 두 개의 메서드로 리팩터링합니다. 새 메서드는 인출로 잔고가 최솟값보다 낮아지면 지정된 작업을 수행합니다. 기존 `MakeWithdrawal` 메서드에는 다음과 같은 코드가 있습니다.

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

다음 코드로 바꿉니다.

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="RefactoredMakeWithdrawal":::

추가된 메서드는 `protected`로, 파생 클래스에서만 호출할 수 있음을 뜻합니다. 이렇게 선언하면 다른 클라이언트가 메서드를 호출할 수 없습니다. 또한 파생 클래스가 동작을 변경할 수 있도록 `virtual`입니다. 반환 형식은 `Transaction?`입니다. `?` 주석은 메서드가 `null`을 반환할 수 있음을 나타냅니다. 인출 한도를 초과할 때 수수료를 청구하기 위해 `LineOfCreditAccount`에 다음 구현을 추가합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="AddOverdraftFee":::

재정의는 계좌에서 초과 인출할 때 수수료 트랜잭션을 반환합니다. 인출이 한도를 초과하지 않으면 메서드는 `null` 트랜잭션을 반환합니다. 이는 수수료가 없음을 나타냅니다. `Program` 클래스의 `Main` 메서드에 다음 코드를 추가하여 이러한 변경 내용을 테스트합니다.

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

프로그램을 실행하고 결과를 확인합니다.

## <a name="summary"></a>요약

잘 알 수 없는 경우 [GitHub 리포지토리](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/object-oriented-programming)에서 이 자습서의 소스를 확인할 수 있습니다.

이 자습서에서 개체 지향 프로그래밍에 사용되는 다양한 방법을 살펴봤습니다.

- 각 클래스에 많은 세부 정보를 `private`으로 유지하는 경우 추상화를 사용했습니다.
- 서로 다른 각 계좌 유형의 클래스를 정의할 때 캡슐화를 사용했습니다. 이러한 클래스는 해당 계좌 유형의 동작을 설명합니다.
- `BankAccount` 클래스에서 이미 만든 구현을 활용하여 코드를 저장하는 경우 상속을 사용했습니다.
- 파생 클래스가 해당 계좌 유형의 특정 동작을 만들기 위해 재정의할 수 있는 `virtual` 메서드를 만들 때 다형성을 사용했습니다.

축하합니다. 모든 C# 소개 자습서를 완료했습니다. 더 자세한 내용은 추가 [자습서](../index.md)를 확인하세요.
