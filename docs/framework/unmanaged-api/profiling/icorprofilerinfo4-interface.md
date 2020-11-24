---
title: ICorProfilerInfo4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c3e623b0b5f8b49e043fe3a1aa8311558e573573
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682837"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4 인터페이스

코드 프로파일러가 CLR (공용 언어 런타임)과 통신 하 여 이벤트 모니터링 및 요청 정보를 제어 하는 데 사용 하는 메서드를 제공 합니다. . `ICorProfilerInfo4`인터페이스는 다른 인터페이스의 확장입니다 `ICorProfilerInfo` . .NET Framework 4.5에 추가 된 JIT (just-in-time) 재컴파일 기능을 지 원하는 새로운 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumJITedFunctions2 메서드](icorprofilerinfo4-enumjitedfunctions2-method.md)|이전에 JIT 컴파일된 후 JIT 다시 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.|  
|[EnumThreads 메서드](icorprofilerinfo4-enumthreads-method.md)|프로 파일링 된 프로세스에서 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 가져옵니다.|  
|[GetCodeInfo3 메서드](icorprofilerinfo4-getcodeinfo3-method.md)|지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.|  
|[GetFunctionFromIP2 메서드](icorprofilerinfo4-getfunctionfromip2-method.md)|관리 되는 코드 명령 포인터를 지정 된 함수의 JIT 다시 컴파일된 버전에 매핑합니다.|  
|[GetILToNativeMapping2 메서드](icorprofilerinfo4-getiltonativemapping2-method.md)|지정 된 함수의 JIT 다시 컴파일된 버전에 포함 된 코드에 대 한 MSIL (Microsoft 중간 언어) 오프셋과 네이티브 오프셋 간의 맵을 가져옵니다.|  
|[GetObjectSize2 메서드](icorprofilerinfo4-getobjectsize2-method.md)|지정 된 개체의 크기를 반환 합니다.|  
|[GetReJITIDs 메서드](icorprofilerinfo4-getrejitids-method.md)|아직 할당 된 지정 된 함수의 JIT 다시 컴파일된 모든 버전을 식별 하는 Id 배열을 반환 합니다.|  
|[InitializeCurrentThread 메서드](icorprofilerinfo4-initializecurrentthread-method.md)|교착 상태를 방지할 수 있도록 동일한 스레드에서 후속 프로파일러 API 호출을 앞서 현재 스레드를 초기화 합니다.|  
|[RequestReJIT 메서드](icorprofilerinfo4-requestrejit-method.md)|지정된 함수의 모든 인스턴스에 대한 JIT 다시 컴파일을 요청합니다.|  
|[RequestRevert 메서드](icorprofilerinfo4-requestrevert-method.md)|지정된 함수의 모든 인스턴스를 원래 버전으로 되돌립니다.|  
  
## <a name="remarks"></a>설명  

 CLR은 자유 스레드 모델을 사용하여 `ICorProfilerInfo4` 인터페이스의 메서드를 구현합니다. 각 메서드가 HRESULT를 반환하여 성공 또는 실패를 나타냅니다. 가능한 반환 코드 목록은 CorError.h 파일을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
