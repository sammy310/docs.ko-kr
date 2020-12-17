---
title: try-catch를 사용하여 예외를 처리하는 방법 - C# 프로그래밍 가이드
description: try-catch 블록을 사용하여 예외를 처리하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: b6368660dbe037123f5bb6ce52502d4a94fcfc3a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110522"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>try-catch를 사용하여 예외를 처리하는 방법(C# 프로그래밍 가이드)

[try-catch](../../language-reference/keywords/try-catch.md) 블록은 작업 코드에서 생성된 예외를 catch하고 처리하기 위한 것입니다. 일부 예외는 `catch` 블록에서 처리될 수 있으며, 예외가 다시 throw되지 않고 문제가 해결됩니다. 그러나 대체로 수행할 수 있는 작업은 적절한 예외가 throw되었는지 확인하는 것뿐입니다.

## <a name="example"></a>예제

이 예제에서 <xref:System.IndexOutOfRangeException>은 가장 적합한 예외가 아닙니다. 호출자가 전달한 `index` 인수로 인해 오류가 발생하기 때문에 <xref:System.ArgumentOutOfRangeException>이 메서드에 더 적합합니다.

:::code language="csharp" source="snippets/exceptions/ExampleTryCatch.cs" id="ExampleTryCatch":::

## <a name="comments"></a>설명

예외가 발생하는 코드는 `try` 블록으로 묶여 있습니다. `IndexOutOfRangeException`이 발생할 경우 처리하기 위해 `catch` 문이 바로 뒤에 추가됩니다. `catch` 블록은 `IndexOutOfRangeException`을 처리하고 더 적합한 `ArgumentOutOfRangeException` 예외를 대신 throw합니다. 호출자에게 최대한 많은 정보를 제공하기 위해 원래 예외를 새 예외의 <xref:System.Exception.InnerException%2A>으로 지정하는 것이 좋습니다. <xref:System.Exception.InnerException%2A> 속성은 [읽기 전용](../../properties.md#read-only)이기 때문에 새 예외의 생성자에 할당해야 합니다.
