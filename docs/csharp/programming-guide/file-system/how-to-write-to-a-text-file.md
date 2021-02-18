---
title: 텍스트 파일에 쓰는 방법 - C# 프로그래밍 가이드
description: C#를 사용하여 텍스트 파일을 작성하는 방법을 알아봅니다. 몇 가지 코드 예제와 사용 가능한 추가 리소스를 확인합니다.
ms.date: 02/11/2021
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.topic: how-to
ms.custom: contperf-fy21q3
ms.openlocfilehash: ecc3ba73161d4f4571bbc6ae0c9aaa3337586ef7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475619"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>텍스트 파일에 쓰는 방법(C# 프로그래밍 가이드)

이 문서에는 파일에 텍스트를 쓰는 다양한 방법을 보여 주는 몇 가지 예제가 있습니다. 처음 두 예제에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스의 정적 편의 메서드를 사용하여 `IEnumerable<string>`의 각 요소와 `string`을 텍스트 파일에 씁니다. 세 번째 예제에서는 파일에 쓸 때 각 줄을 개별적으로 처리해야 하는 경우 파일에 텍스트를 추가하는 방법을 보여 줍니다. 처음 세 예제에서는 파일의 모든 기존 콘텐츠를 덮어씁니다. 마지막 예제에서는 기존 파일에 텍스트를 추가하는 방법을 보여 줍니다.

 이 예에서는 파일에 모든 문자열 리터럴을 작성합니다. 파일에 작성된 텍스트의 서식을 지정하려면 <xref:System.String.Format%2A> 메서드 또는 C# [문자열 보간](../../language-reference/tokens/interpolated.md) 기능을 사용합니다.

## <a name="write-a-collection-of-strings-to-a-file"></a>파일에 문자열 컬렉션 쓰기

:::code language="csharp" source="snippets/write-text/WriteAllLines.cs":::

이전 소스 코드 예제는 다음과 같습니다.

- 세 개 값이 있는 문자열 배열을 인스턴스화합니다.
- 다음과 같은 <xref:System.IO.File.WriteAllLinesAsync%2A?displayProperty=nameWithType> 호출을 기다립니다.

  - 파일 이름 *WriteLines.txt* 를 비동기적으로 만듭니다. 파일이 이미 있으면 덮어씁니다.
  - 지정된 줄을 파일에 씁니다.
  - 파일을 닫아 필요에 따라 자동으로 플러시하고 삭제합니다.

## <a name="write-one-string-to-a-file"></a>파일에 하나의 문자열 쓰기

:::code language="csharp" source="snippets/write-text/WriteAllText.cs":::

이전 소스 코드 예제는 다음과 같습니다.

- 할당된 문자열 리터럴이 제공된 문자열을 인스턴스화합니다.
- 다음과 같은 <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> 호출을 기다립니다.

  - 파일 이름 *WriteText.txt* 를 비동기적으로 만듭니다. 파일이 이미 있으면 덮어씁니다.
  - 지정된 텍스트를 파일에 씁니다.
  - 파일을 닫아 필요에 따라 자동으로 플러시하고 삭제합니다.

## <a name="write-selected-strings-from-an-array-to-a-file"></a>파일에 배열에서 선택한 문자열 쓰기

:::code language="csharp" source="snippets/write-text/StreamWriterOne.cs":::

이전 소스 코드 예제는 다음과 같습니다.

- 세 개 값이 있는 문자열 배열을 인스턴스화합니다.
- *WriteLines2.txt* 의 파일 경로를 [using 선언](../../whats-new/csharp-8.md#using-declarations)으로 사용하여 <xref:System.IO.StreamWriter>를 인스턴스화합니다.
- 모든 줄을 반복합니다.
- 줄에 `"Second"`가 포함되지 않은 경우 해당 줄을 파일에 쓰는 <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType> 호출을 조건에 따라 기다립니다.

## <a name="append-text-to-an-existing-file"></a>기존 파일에 텍스트 추가

:::code language="csharp" source="snippets/write-text/StreamWriterTwo.cs":::

이전 소스 코드 예제는 다음과 같습니다.

- 세 개 값이 있는 문자열 배열을 인스턴스화합니다.
- *WriteLines2.txt* 의 파일 경로를 [using 선언](../../whats-new/csharp-8.md#using-declarations)으로 사용하여 <xref:System.IO.StreamWriter>를 인스턴스화하고 추가할 `true`를 전달합니다.
- 문자열을 파일에 추가된 줄로 쓰는 <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType> 호출을 기다립니다.

## <a name="exceptions"></a>예외

다음 조건에서 예외가 발생합니다.

- <xref:System.InvalidOperationException>: 파일이 있지만 읽기 전용인 경우
- <xref:System.IO.PathTooLongException>: 경로 이름이 너무 긴 경우
- <xref:System.IO.IOException>: 디스크가 꽉 찬 경우

파일 시스템을 사용하는 경우 예외를 발생시킬 수 있는 추가 조건이 있습니다. 방어적으로 프로그래밍하는 것이 좋습니다.

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](./index.md)
- [샘플: 애플리케이션 스토리지에 컬렉션 저장](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
