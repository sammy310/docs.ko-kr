---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802499"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>WPF 맞춤법 검사기에 의해 throw된 ObjectDisposedException

|   |   |
|---|---|
|세부 정보|WPF 애플리케이션은 애플리케이션 종료 중에 맞춤법 검사기에서 throw된 <xref:System.ObjectDisposedException?displayProperty=name>으로 인해 때때로 크래시됩니다. 이는 .NET Framework 4.7 WPF에서 예외를 제대로 처리하여 애플리케이션이 더 이상 부정적인 영향을 받지 않도록 함으로써 해결되었습니다. 디버거에서 실행 중인 애플리케이션에서는 경우에 따라 첫째 예외만 계속 확인될 수 있습니다.|
|제안 해결 방법|NET Framework 4.7로 업그레이드|
|범위|가장자리|
|Version|4.6.1|
|형식|런타임|
