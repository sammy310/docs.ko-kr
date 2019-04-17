---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235563"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.

|   |   |
|---|---|
|세부 정보|System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.|
|제안 해결 방법|이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다. 이제 <xref:System.OverflowException?displayProperty=name> 예외가 throw됩니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
