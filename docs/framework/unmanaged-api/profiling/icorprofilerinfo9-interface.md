---
description: '자세히 알아보기: ICorProfilerInfo9 인터페이스'
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 954cb16d2b789359693f6a8fa3e0f6e19ad19b3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736910"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9 인터페이스

여러 네이티브 코드 버전이 있는 함수에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo8](icorprofilerinfo8-interface.md) 의 서브 클래스입니다.  

## <a name="methods"></a>메서드  

| 메서드|설명|  
| ------------|-----------------|  
|[GetNativeCodeStartAddresses 메서드](icorprofilerinfo9-getnativecodestartaddresses-method.md)| FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다. |
|[GetILToNativeMapping3 메서드](icorprofilerinfo9-getiltonativemapping3-method.md)| 네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다. |
|[GetCodeInfo4 메서드](icorprofilerinfo9-getcodeinfo4-method.md)| 네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다. |

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
