---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117246"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a>"C" 로캘이 고정 로캘에 매핑됩니다

.NET Core 2.2 및 이전 버전은 "C" 로캘을 en_US_POSIX 로캘에 매핑하는 기본 ICU 동작에 의존합니다. en_US_POSIX 로캘은 대/소문자를 구분하지 않는 문자열 비교를 지원하지 않으므로 원치 않는 데이터 정렬 동작이 있습니다. 일부 Linux 배포판에서는 "C" 로캘을 기본 로캘로 설정하므로 사용자가 예기치 않은 동작을 경험했습니다. 

#### <a name="details"></a>세부 정보

.NET Core 3.0부터 "C" 로캘 매핑이 en_US_POSIX 대신 고정 로캘을 사용하도록 변경되었습니다. "C" 로캘의 고정 로캘 매핑은 일관성을 위해 Windows에도 적용됩니다.

en_US_POSIX는 대/소문자를 구분하지 않는 정렬/검색 문자열 작업을 지원하지 않기 때문에 "C"를 en_US_POSIX 문화권에 매핑 시 고객의 혼란이 발생했습니다. "C" 로캘이 일부 Linux 배포판에서 기본 로캘로 사용되므로 고객이 이러한 운영 체제에서 이 원치 않는 동작을 경험했습니다. 

#### <a name="version-introduced"></a>도입된 버전

.NET Core 3.0

### <a name="recommended-action"></a>권장 작업

이 변경 내용을 아는 것 외에 특별히 다른 것은 없습니다. 이러한 변경 내용은 “C” 로캘을 사용하는 애플리케이션에만 영향을 줍니다.

### <a name="category"></a>범주

전역화 

### <a name="affected-apis"></a>영향을 받는 API

모든 데이터 정렬 및 문화권 API는 이 변경 내용의 영향을 받습니다.

<!--

-->
