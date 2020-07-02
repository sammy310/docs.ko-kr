---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621840"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>예기치 않은 방식으로 WPF 맞춤법 검사가 실패

#### <a name="details"></a>설명

여기에는 WPF 맞춤법 검사기의 여러 문제가 포함됩니다.<ul><li>WPF 맞춤법 검사기가 때때로 <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName>을 throw</li><li>'다른 사용자로 실행'을 사용하여 애플리케이션을 시작하면 WPF 맞춤법 검사기가 <xref:System.UnauthorizedAccessException>과 함께 실패</li><li>WPF 맞춤법 검사기가 독일어의 'Hausnummer'와 같은 복합어의 맞춤법 오류를 잘못 식별합니다.</li></ul>

#### <a name="suggestion"></a>제안 해결 방법

문제 #1 - .NET Framework 4.6.2에서 해결되었습니다. 문제 #2 - '다른 사용자로 실행'을 사용하여 애플리케이션을 시작할 때 WPF 맞춤법 검사기가 더 이상 지원되지 않습니다. .NET Framework 4.6.2부터 이러한 방식으로 시작된 애플리케이션이 더 이상 예기치 않게 크래시되지 않습니다. - 대신 맞춤법 검사기가 자동으로 비활성화됩니다. 문제 #3 - .NET Framework 4.6.2에서 해결되었습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6.1|
|형식|런타임|
