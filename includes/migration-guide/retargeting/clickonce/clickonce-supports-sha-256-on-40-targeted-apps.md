---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804582"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce가 4.0 대상 앱에서 SHA-256 지원

|   |   |
|---|---|
|세부 정보|이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET Framework 4.5 이상이 필요했습니다. 이제 .NET Framework 4.0을 대상으로 하는 ClickOnce 앱을 SHA-256으로 서명한 경우에도 .NET Framework 4.0에서 실행할 수 있습니다.|
|제안 해결 방법|이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.|
|범위|사소함|
|Version|4.6|
|형식|대상 변경|
