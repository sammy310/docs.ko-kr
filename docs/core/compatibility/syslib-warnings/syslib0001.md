---
title: SYSLIB0001 경고
description: 컴파일 시간 경고 SYSLIB0001을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 6c4b6a2f41e9dc044ef76bb5a53a4a54a44bca5a
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596381"
---
# <a name="syslib0001-the-utf-7-encoding-is-insecure"></a>SYSLIB0001: UTF-7 인코딩이 안전하지 않음

UTF-7 인코딩은 더 이상 애플리케이션에서 광범위하게 사용되지 않으며, 이제 많은 사양에서는 교환에 [사용을 금지](https://security.stackexchange.com/a/68609/3573)합니다. 간혹 UTF-7로 인코딩된 데이터를 기대하지 않는 애플리케이션에서 [공격 벡터로 사용](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7)되기도 합니다. 오류 검색 기능이 제공되지 않기 때문에 Microsoft는 <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>을 사용하지 않도록 경고합니다.

따라서 다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0001` 경고가 생성됩니다.

- <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 속성
- <xref:System.Text.UTF7Encoding.%23ctor%2A> 생성자

## <a name="workarounds"></a>해결 방법

- 사용자 고유의 프로토콜 또는 파일 형식에서 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 또는 <xref:System.Text.UTF7Encoding>을 사용하는 경우:

  <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> 또는 <xref:System.Text.UTF8Encoding>을 사용하도록 전환합니다. UTF-8은 업계 표준이며 광범위한 언어, 운영 체제 및 런타임에서 지원됩니다. UTF-8을 사용하면 나중에 코드를 더 쉽게 유지 관리할 수 있으며, 나머지 에코시스템과 상호 운용이 더 간단해집니다.

- <xref:System.Text.Encoding> 인스턴스를 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>과 비교하는 경우:

  대신, 잘 알려진 UTF-7 코드 페이지 `65000`에 대해 검사를 수행하는 것이 좋습니다. 이 코드 페이지와 비교하여 경고를 방지하고, 다른 사용자가 `new UTF7Encoding()`를 호출했거나 형식이 서브클래싱된 경우와 같은 일부 특수한 사례를 처리합니다.

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>추가 정보

- [UTF-7 코드 경로가 사용되지 않음](../core-libraries/5.0/utf-7-code-paths-obsolete.md)
