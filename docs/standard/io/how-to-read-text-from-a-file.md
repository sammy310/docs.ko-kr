---
title: '방법: 파일에서 텍스트 읽기'
description: 이 문서에서 데스크톱용 .NET 앱에서 StreamReader 클래스를 사용하여 텍스트 파일에서 텍스트를 동기 또는 비동기적으로 읽는 방법의 예제를 확인하세요.
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 0d8dfae67ede779a611204fb333a19defcaee8e6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382128"
---
# <a name="how-to-read-text-from-a-file"></a>방법: 파일에서 텍스트 읽기
다음 예제에서는 데스크톱 응용 프로그램용 .NET을 사용하여 텍스트 파일에서 텍스트를 동기 또는 비동기적으로 읽는 방법을 보여줍니다. 두 예제에서는 <xref:System.IO.StreamReader> 클래스의 인스턴스를 만들 때 파일의 상대 또는 절대 경로를 제공합니다.
  
> [!NOTE]
> Windows 런타임에서는 파일을 읽고 파일에 쓰는 다양한 스트림 형식을 제공하기 때문에 이러한 코드 예제는 UWP(유니버설 Windows 플랫폼) 앱 개발에는 적용되지 않습니다. UWP 앱에서 파일의 텍스트를 읽는 방법을 보여주는 예제는 [빠른 시작: 파일 읽기 및 쓰기](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10))를 참조하세요. .NET Framework 스트림과 Windows 런타임 스트림 간의 변환 방법을 보여주는 예제는 [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](how-to-convert-between-dotnet-streams-and-winrt-streams.md)을 참조하세요.  
  
## <a name="example-synchronous-read-in-a-console-app"></a>예: 콘솔 앱 내에서 동기식 읽기  
다음 예제에서는 콘솔 앱 내에서 동기식 읽기 작업을 보여줍니다. 이 예제에서는 스트림 판독기를 사용하여 텍스트 파일을 열고 콘텐츠를 문자열로 복사한 다음, 콘솔에 문자열을 출력합니다.  
  
> [!IMPORTANT]
> 이 예제에서는 *TestFile.txt* 파일이 앱과 동일한 폴더에 이미 존재한다고 가정합니다.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>예: WPF 앱에서 비동기식 읽기
 다음 예제에서는 WPF(Windows Presentation Foundation) 앱에서 비동기식 읽기 작업을 보여줍니다.  
  
> [!IMPORTANT]
> 이 예제에서는 *TestFile.txt* 파일이 앱과 동일한 폴더에 이미 존재한다고 가정합니다.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a>참조

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [비동기 파일 I/O](asynchronous-file-i-o.md)  
- [방법: 디렉터리 목록 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [빠른 시작: 파일 읽기 및 쓰기](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [방법: 새로 만든 데이터 파일 읽기 및 쓰기](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [방법: 로그 파일 열기 및 추가](how-to-open-and-append-to-a-log-file.md)  
- [방법: 파일에 텍스트 쓰기](how-to-write-text-to-a-file.md)  
- [방법: 문자열에서 문자 읽기](how-to-read-characters-from-a-string.md)  
- [방법: 문자열에 문자 쓰기](how-to-write-characters-to-a-string.md)  
- [파일 및 스트림 I/O](index.md)
