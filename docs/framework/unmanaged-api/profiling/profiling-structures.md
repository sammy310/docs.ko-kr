---
description: '자세한 정보: 프로 파일링 구조'
title: 프로파일링 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 176830cac519f22864ba004b176cb575d80e50e2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760238"
---
# <a name="profiling-structures"></a>프로파일링 구조체

이 섹션에서는 프로파일링 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체](cor-prf-assembly-reference-info-structure.md)  
 어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 참조 어셈블리에 대한 정보를 공용 언어 런타임에 제공합니다.  
  
 [COR_PRF_CODE_INFO 구조체](cor-prf-code-info-structure.md)  
 메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.  
  
 [COR_PRF_EX_CLAUSE_INFO 구조체](cor-prf-ex-clause-info-structure.md)  
 특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.  
  
 [COR_PRF_FUNCTION 구조체](cor-prf-function-structure.md)  
 함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.  
  
 [COR_PRF_FUNCTION_ARGUMENT_INFO 구조체](cor-prf-function-argument-info-structure.md)  
 왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.  
  
 [COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체](cor-prf-function-argument-range-structure.md)  
 왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.  
  
 [COR_PRF_GC_GENERATION_RANGE 구조체](cor-prf-gc-generation-range-structure.md)  
 가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.  

 [COR_PRF_EVENTPIPE_PROVIDER_CONFIG 구조체](cor-prf-eventpipe-provider-config-structure.md) EventPipe 공급자를 구성 하는 데 필요한 필드에 대해 설명 합니다.

 [COR_PRF_EVENTPIPE_PARAM_DESC 구조체](cor-prf-eventpipe-param-desc-structure.md) EventPipe 이벤트의 매개 변수 이름 및 유형을 설명 합니다.

 [COR_PRF_EVENT_DATA 구조체](cor-prf-event-data-structure.md) 작성 중인 EventPipe 이벤트에 대 한 이벤트 데이터를 설명 합니다.
  
## <a name="related-sections"></a>관련 단원  

 COR_DEBUG_IL_TO_NATIVE_MAP  
  
 COR_IL_MAP  
  
 [프로파일링 개요](profiling-overview.md)  
  
 [프로파일링 인터페이스](profiling-interfaces.md)  
  
 [프로파일링 전역 정적 함수](profiling-global-static-functions.md)  
  
 [프로파일링 열거형](profiling-enumerations.md)
