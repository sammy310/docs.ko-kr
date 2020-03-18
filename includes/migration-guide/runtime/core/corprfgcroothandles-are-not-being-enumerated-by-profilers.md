---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858571"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>프로파일러에서 COR_PRF_GC_ROOT_HANDLE을 열거하지 않습니다.

|   |   |
|---|---|
|세부 정보|.NET Framework v4.5.1에서 프로파일링 API <code>RootReferences2()</code>가 <code>COR_PRF_GC_ROOT_HANDLE</code>를 절대 반환하지 않습니다(대신 <code>COR_PRF_GC_ROOT_OTHER</code>로 반환). 이 문제는 .NET Framework 4.6부터 해결되었습니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|
|범위|사소함|
|Version|4.5.1|
|형식|런타임|
