---
title: '방법: 웹 페이지 요청 및 결과를 스트림으로 검색'
description: 이 예제에서는 .NET Framework에서 웹 페이지를 요청하고 스트림에서 결과를 검색하는 방법을 보여 줍니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502485"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>방법: 웹 페이지 요청 및 결과를 스트림으로 검색

이 예제에서는 웹 페이지를 요청하고 스트림에서 결과를 검색하는 방법을 보여 줍니다.
  
## <a name="example"></a>예제

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a>코드 컴파일

 이 예제에는 다음 사항이 필요합니다.

- <xref:System.IO> 및 <xref:System.Net> 네임스페이스에 대한 참조

## <a name="see-also"></a>참조

- [데이터 요청](requesting-data.md)
