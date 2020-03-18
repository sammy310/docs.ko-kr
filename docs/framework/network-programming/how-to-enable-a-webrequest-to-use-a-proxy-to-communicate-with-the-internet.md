---
title: '방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039546"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정

이 예제에서는 인터넷과 통신하는 데 프록시를 사용하기 위해 <xref:System.Net.WebRequest>를 사용하도록 설정할 전역 프록시 인스턴스를 만듭니다. 예제에서는 프록시 서버의 이름이 `webproxy`이고 표준 HTTP 포트인 포트 80에서 통신한다고 가정합니다.

## <a name="example"></a>예제

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

- [System.Net`using` 네임스페이스에 대한 C# ](../../csharp/language-reference/keywords/using-directive.md) **지시문**
- [System.Net`Imports` 네임스페이스에 대한 Visual Basic ](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) **문**

## <a name="see-also"></a>참고 항목

- [애플리케이션 프로토콜 사용](using-application-protocols.md)
- [프록시를 통해 인터넷 액세스](accessing-the-internet-through-a-proxy.md)
