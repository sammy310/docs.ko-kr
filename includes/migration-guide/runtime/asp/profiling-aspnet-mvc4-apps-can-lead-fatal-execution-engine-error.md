---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235527"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>ASP.Net MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있습니다.

|   |   |
|---|---|
|세부 정보|NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 애플리케이션을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.5.2에서 해결되었습니다. 또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
