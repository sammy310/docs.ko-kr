---
title: 예외 처리 - C# 프로그래밍 가이드
description: 예외 처리에 대해 알아봅니다. try-catch, try-finally 및 try-catch-finally 문 예제를 살펴봅니다.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: fabf1413ba498232e67f45460195fe96e25fab0a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110197"
---
# <a name="exception-handling-c-programming-guide"></a>예외 처리(C# 프로그래밍 가이드)

[try](../../language-reference/keywords/try-catch.md) 블록은 C# 프로그래머가 예외의 영향을 받을 수 있는 코드를 분할하는 데 사용됩니다. 연결된 [catch](../../language-reference/keywords/try-catch.md) 블록은 결과 예외를 처리하는 데 사용됩니다. [finally](../../language-reference/keywords/try-finally.md) 블록에는 `try` 블록에서 할당되는 리소스 해제와 같이 `try` 블록에서 예외가 throw되는지 여부와 관계없이 실행되는 코드가 포함됩니다. `try` 블록에는 하나 이상의 연결된 `catch` 블록, `finally` 블록 또는 둘 다가 필요합니다.

다음 예제에서는 `try-catch` 문, `try-finally` 문 및 `try-catch-finally` 문을 보여 줍니다.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryFinallyStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchFinallyStructure":::

`try` 블록에 `catch` 또는 `finally` 블록이 없으면 컴파일러 오류가 발생합니다.

## <a name="catch-blocks"></a>catch 블록

`catch` 블록에서는 catch할 예외의 형식을 지정할 수 있습니다. 형식 사양을 *예외 필터* 라고 합니다. 예외 형식은 <xref:System.Exception>에서 파생되어야 합니다. 일반적으로 `try` 블록에서 throw될 수 있는 모든 예외를 처리하는 방법을 알고 있거나 `catch` 블록의 끝에 [throw](../../language-reference/keywords/throw.md) 문을 포함한 경우가 아니라면 <xref:System.Exception>을 예외 필터로 지정하지 마세요.

다른 예외 클래스를 사용하는 여러 `catch` 블록을 함께 연결할 수 있습니다. `catch` 블록은 코드의 위에서 아래로 계산되지만 throw되는 각 예외에 대해 하나의 `catch` 블록만 실행됩니다. throw된 예외의 정확한 형식이나 기본 클래스를 지정하는 첫 번째 `catch` 블록이 실행됩니다. `catch` 블록에서 일치하는 예외 클래스를 지정하지 않으면 `catch` 블록이 문에 있는 경우 어느 형식도 없는 블록이 선택됩니다. 먼저 가장 구체적인(즉, 최다 파생) 예외 클래스를 사용하여 `catch` 블록을 배치해야 합니다.

다음 조건을 충족하는 경우 예외를 catch합니다.

- 예외가 throw되는 이유를 충분히 이해하고 있으면 <xref:System.IO.FileNotFoundException> 개체를 catch할 때 새 파일 이름을 입력하라는 메시지를 사용자에게 표시하는 경우처럼 구체적인 복구를 구현할 수 있습니다.
- 보다 구체적인 새 예외를 생성하고 throw할 수 있습니다.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowMoreSpecificException":::
- 추가 처리를 위해 예외를 전달하기 전에 부분적으로 처리하려고 합니다. 다음 예제에서 `catch` 블록은 예외를 다시 throw하기 전에 오류 로그에 항목을 추가하는 데 사용됩니다.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="RethrowError":::

‘예외 필터’를 지정하여 catch 절에 부울 식을 추가할 수도 있습니다. 이렇게 하면 해당 조건이 true인 경우에만 특정 catch 절이 일치합니다. 다음 예제에서는 두 catch 절에서 같은 예외 클래스를 사용하지만 추가 조건을 확인하여 다른 오류 메시지를 생성합니다.

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="DemonstrateExceptionFilter":::

항상 `false`를 반환하는 예외 필터를 사용하여 모든 예외를 검사하지만 처리하지는 않을 수 있습니다. 일반적인 용도는 예외를 기록하는 것입니다.

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="ShowExceptionFilter":::

`LogException` 메서드는 항상 `false`를 반환하므로 이 예외 필터를 사용하는 `catch` 절 중 어느 것도 일치하지 않습니다. catch 절은 <xref:System.Exception?displayProperty=nameWithType>을 사용하는 범용일 수 있으며 이후 절이 더 구체적인 예외 클래스를 처리할 수 있습니다.

## <a name="finally-blocks"></a>Finally 블록

`finally` 블록에서는 `try` 블록에서 수행된 작업을 정리할 수 있습니다. `finally` 블록이 있는 경우 `try` 블록 및 일치하는 모든 `catch` 블록 다음에 마지막으로 실행됩니다. `finally` 블록은 예외가 throw되었는지 또는 예외 형식과 일치하는 `catch` 블록이 있는지와 관계없이 항상 실행됩니다.

`finally` 블록은 런타임의 가비지 수집기가 개체를 종료할 때까지 기다리지 않고 파일 스트림, 데이터베이스 연결, 그래픽 핸들 등의 리소스를 해제하는 데 사용됩니다. 자세한 내용은 [using 문](../../language-reference/keywords/using-statement.md)을 참조하세요.

다음 예제에서는 `finally` 블록을 사용하여 `try` 블록에서 연 파일을 닫습니다. 파일을 닫기 전에 파일 핸들의 상태를 확인해야 합니다. `try` 블록에서 파일을 열 수 없는 경우 파일 핸들은 값이 `null`이며 `finally` 블록은 파일을 닫지 않습니다. 대신 `try` 블록에서 파일을 연 경우 `finally` 블록에서 열려 있는 파일을 닫습니다.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CleanupIfNotNull":::

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [예외](~/_csharplang/spec/exceptions.md) 및 [try 문](~/_csharplang/spec/statements.md#the-try-statement)을 참조하세요. 언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.
  
## <a name="see-also"></a>참조

- [C# 참조](../../language-reference/index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [using 문](../../language-reference/keywords/using-statement.md)
