---
title: using 문 - C# 참조
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 52cde99fd029ce50f159b2a87fbfbf47fc79dccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712964"
---
# <a name="using-statement-c-reference"></a>using 문(C# 참조)

<xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.

## <a name="example"></a>예제

다음 예제에서는 `using` 문을 사용하는 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

C# 8.0부터는 중괄호가 필요하지 않은 `using` 문에 다음 대체 구문을 사용할 수 있습니다.

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a>설명

<xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 디바이스 컨텍스트). 다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다. 이러한 형식은 모두 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.

`IDisposable` 개체의 수명이 단일 메서드로 제한된 경우 `using` 문에서 선언하고 인스턴스화해야 합니다. `using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다. `using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.

`using` 문은 <xref:System.IDisposable.Dispose%2A> 블록 내에서 예외가 발생하더라도 `using`가 호출되도록 합니다. `try` 블록 내부에 개체를 배치한 다음, <xref:System.IDisposable.Dispose%2A> 블록에서 `finally`를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다. 이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

최신 `using` 문 구문은 매우 유사한 코드로 변환됩니다. 변수가 선언된 위치에서 `try` 블록이 열립니다. `finally` 블록은 일반적으로 메서드의 끝에 있는 바깥쪽 블록의 가까이에 추가됩니다.

`try`-`finally` 문에 대한 자세한 내용은 [try-finally](try-finally.md) 항목을 참조하세요.

다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

C# 8에 도입된 새로운 구문을 사용하여 동일한 형식의 여러 선언을 결합할 수 있습니다. 이는 다음 예제에서 확인할 수 있습니다.

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다. 이 경우 컨트롤이 `using` 블록을 벗어난 후에도 개체가 범위 내에 있지만, 관리되지 않는 리소스에 액세스하지 못할 수 있습니다. 즉, 더 이상 완전히 초기화되지 않습니다. `using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다. 따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

`IDisposable` 개체를 삭제하는 방법에 대한 자세한 내용은 [IDisposable을 구현하는 개체 사용](../../../standard/garbage-collection/using-objects.md)을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/statements.md#the-using-statement)의 [using 문](/dotnet/csharp/language-reference/language-specification/introduction)을 참조하세요. 언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [using 지시문](using-directive.md)
- [가비지 수집](../../../standard/garbage-collection/index.md)
- [IDisposable을 구현하는 개체 사용](../../../standard/garbage-collection/using-objects.md)
- [IDisposable 인터페이스](xref:System.IDisposable)
- [C# 8.0의 using 문](~/_csharplang/proposals/csharp-8.0/using.md)
