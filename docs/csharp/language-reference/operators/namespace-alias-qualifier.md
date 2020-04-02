---
title: ':: 연산자 - C# 참조'
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 84c418627462f83630fe5072a0b0e2089f6588f6
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507128"
---
# <a name="-operator-c-reference"></a>:: 연산자(C# 참조)

네임스페이스 별칭 한정자(`::`)를 사용하여 별칭이 지정된 네임스페이스의 구성원에 액세스합니다. 두 식별자 사이에 `::` 한정사만 사용할 수 있습니다. 왼쪽 식별자는 다음 별칭 중 하나를 사용할 수 있습니다.

- [별칭 지시문을 사용](../keywords/using-directive.md)하여 만든 네임스페이스 별칭:

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- [extern 별칭](../keywords/extern-alias.md)
- 전역 네임스페이스 별칭인 `global` 별칭. 전역 네임스페이스는 명명된 네임스페이스 내에 선언되지 않은 네임스페이스와 형식을 포함하는 네임스페이스입니다. `::` 한정자와 함께 사용하는 경우 `global` 별칭은 사용자 정의 `global` 네임 스페이스 별칭이 있더라도 항상 전역 네임 스페이스를 참조합니다.

  다음 예제에서는 `global` 별칭을 사용하여 전역 네임스페이스의 구성원인 .NET <xref:System> 네임 스페이스에 액세스합니다. `global` 별칭을 사용하지 않으면 `MyCompany.MyProduct` 네임스페이스의 구성원인 사용자 정의 `System` 네임스페이스에 액세스할 수 있습니다.

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }

      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```

  > [!NOTE]
  > `global` 키워드는 `::` 한정자의 왼쪽 식별자인 경우에만 전역 네임 스페이스 별칭입니다.

[`.` 토큰](member-access-operators.md#member-access-expression-)을 사용하여 별칭이 지정된 네임스페이스의 멤버에 액세스할 수도 있습니다. 그러나 `.` 토큰은 형식 멤버에 액세스하는 데도 사용됩니다. `::` 한정자는 이름이 같은 형식 또는 네임 스페이스가 있는 경우에도 해당 왼쪽 식별자가 항상 네임스페이스 별칭을 참조하는지 확인합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [네임스페이스 별칭 한정자](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자](index.md)
- [네임스페이스 사용](../../programming-guide/namespaces/using-namespaces.md)
