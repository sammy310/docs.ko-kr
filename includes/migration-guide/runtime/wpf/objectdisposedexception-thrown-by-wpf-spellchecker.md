---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621831"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>WPF 맞춤법 검사기에 의해 throw된 ObjectDisposedException

#### <a name="details"></a>설명

WPF 애플리케이션은 애플리케이션 종료 중에 맞춤법 검사기에서 throw된 <xref:System.ObjectDisposedException?displayProperty=fullName>으로 인해 때때로 크래시됩니다. 이는 .NET Framework 4.7 WPF에서 예외를 제대로 처리하여 애플리케이션이 더 이상 부정적인 영향을 받지 않도록 함으로써 해결되었습니다. 디버거에서 실행 중인 애플리케이션에서는 경우에 따라 첫째 예외만 계속 확인될 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

NET Framework 4.7로 업그레이드

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6.1|
|형식|런타임|
