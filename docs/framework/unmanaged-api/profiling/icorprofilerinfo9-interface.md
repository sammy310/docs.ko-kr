---
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 74031fd822550f8a0752d02ce0c2d89b2f5ae546
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444957"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9 인터페이스

여러 네이티브 코드 버전이 있는 함수에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) 의 서브 클래스입니다.  

## <a name="methods"></a>메서드  

| 메서드|설명|  
| ------------|-----------------|  
|[GetNativeCodeStartAddresses 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다. |
|[GetILToNativeMapping3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| 네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다. |
|[GetCodeInfo4 메서드](icorprofilerinfo9-getcodeinfo4-method.md)| 네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다. |

## <a name="requirements"></a>요구 사항  
**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>참고자료

- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
