---
description: '자세히 알아보기: ICorProfilerInfo3:: GetThreadStaticAddress2 메서드'
title: ICorProfilerInfo3::GetThreadStaticAddress2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: 6734996435206f9e0c837eba39df1ad81677e54b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794548"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>ICorProfilerInfo3::GetThreadStaticAddress2 메서드

지정된 스레드 및 애플리케이션 도메인의 범위에 있는 지정된 Thread 정적 필드의 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>매개 변수  

 `classId`  
 진행 요청 된 스레드 정적 필드를 포함 하는 클래스의 ID입니다.  
  
 `fieldToken`  
 진행 요청 된 스레드 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `appDomainId`  
 [in] 애플리케이션 도메인의 ID입니다.  
  
 `threadId`  
 진행 요청 된 정적 필드의 범위에 해당 하는 스레드의 ID입니다.  
  
 `ppAddress`  
 제한이 지정 된 스레드 내의 정적 필드 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `GetThreadStaticAddress2`메서드는 다음 중 하나를 반환할 수 있습니다.  
  
- 지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.  
  
- 가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다. 이러한 주소는 가비지 수집 후에 무효화 될 수 있으므로 가비지 수집 후 프로파일러는 이러한 주소를 유효한 것으로 가정 하지 않아야 합니다.  
  
 클래스의 클래스 생성자가 완료 되기 전에는 `GetThreadStaticAddress2` 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 하지만, 일부 정적 필드는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있을 수 있습니다.  
  
 [ICorProfilerInfo2:: GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) 메서드는 `GetThreadStaticAddress2` 메서드와 유사 하지만 응용 프로그램 도메인 인수를 허용 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
