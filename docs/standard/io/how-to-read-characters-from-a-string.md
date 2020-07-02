---
title: '방법: 문자열에서 문자 읽기'
description: .NET에서 문자열의 문자를 읽는 방법을 알아봅니다. 동기적으로 그리고 비동기적으로 문자 읽기의 예제를 참조하세요.
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
ms.openlocfilehash: 40ff144e0899f3560805a31fa76f391afaeccd67
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594844"
---
# <a name="how-to-read-characters-from-a-string"></a>방법: 문자열에서 문자 읽기
다음 코드 예제는 문자열에서 동기식 또는 비동기식으로 문자를 읽는 방법을 보여줍니다.  
  
## <a name="example-read-characters-synchronously"></a>예: 동기식으로 문자 읽기
 이 예제에서는 문자열에서 동기식으로 13자를 읽고, 배열에 저장하고, 표시합니다. 그런 다음, 문자열의 나머지 문자를 읽고, 6번째 요소에서 시작하는 배열에 저장하고, 배열의 콘텐츠를 표시합니다.  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a>예: 비동기식으로 문자 읽기  
 다음 예제는 WPF 앱의 코드입니다. 창 로드 시, 이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤에서 모든 문자를 비동기식으로 읽고 배열에 저장합니다. 그런 다음, 각 문자 또는 공백 문자를 <xref:System.Windows.Controls.TextBlock> 컨트롤의 별도 라인에 비동기식으로 씁니다.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>참조

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [비동기 파일 I/O](asynchronous-file-i-o.md)  
- [방법: 디렉터리 목록 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [방법: 새로 만든 데이터 파일 읽기 및 쓰기](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [방법: 로그 파일 열기 및 추가](how-to-open-and-append-to-a-log-file.md)  
- [방법: 파일에서 텍스트 읽기](how-to-read-text-from-a-file.md)  
- [방법: 파일에 텍스트 쓰기](how-to-write-text-to-a-file.md)  
- [방법: 문자열에 문자 쓰기](how-to-write-characters-to-a-string.md)  
- [파일 및 스트림 I/O](index.md)
