---
ms.openlocfilehash: cbe1b32fa40e509f620845866c7a584e37f49a80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858512"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>기본 앱 도메인에 대한 TargetFrameworkName을 설정하지 않으면 더 이상 null을 기본값으로 하지 않습니다

|   |   |
|---|---|
|세부 정보|이전에는 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name>이 명시적으로 설정되지 않은 경우 기본 앱 도메인에서 null이었습니다. 4\.6부터 기본 응용 프로그램 도메인에 대한 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> 속성은 TargetFrameworkAttribute에서 파생된 기본값을 가집니다(있는 경우). 기본이 아닌 앱 도메인은 명시적으로 재정의되지 않으면 해당 <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name>을 기본 응용 프로그램 도메인(4.6에서 기본값을 null로 하지 않는)에서 계속 상속합니다.|
|제안 해결 방법|코드는 기본값을 null로 하는 <xref:System.AppDomainSetup.TargetFrameworkName>에 종속하지 않도록 업데이트되어야 합니다. 이 속성이 계속 null을 평가해야 하는 경우 명시적으로 해당 값을 설정할 수 있습니다.|
|범위|가장자리|
|Version|4.6|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
