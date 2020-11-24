---
title: ICorProfilerInfo2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
ms.openlocfilehash: 6c146f3deed31601411bef39ab12b52dfec8cd39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681584"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2 인터페이스

코드 프로파일러가 CLR (공용 언어 런타임)과 통신 하 여 이벤트 모니터링 및 요청 정보를 제어 하는 데 사용 하는 메서드를 제공 합니다. `ICorProfilerInfo2`인터페이스는 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스의 확장입니다. 즉, .NET Framework 버전 2.0 이상 버전에서 지원 되는 새 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DoStackSnapshot 메서드](icorprofilerinfo2-dostacksnapshot-method.md)|관리 되는 호출 프레임을 프로파일러에 보고 하는 지정 된 스레드의 스택을 안내 합니다.|  
|[EnumModuleFrozenObjects 메서드](icorprofilerinfo2-enummodulefrozenobjects-method.md)|지정 된 모듈의 고정 된 개체를 반복할 수 있는 열거자를 가져옵니다.|  
|[GetAppDomainStaticAddress 메서드](icorprofilerinfo2-getappdomainstaticaddress-method.md)|지정 된 응용 프로그램 도메인의 범위에 있는 지정 된 응용 프로그램 도메인 정적 필드의 주소를 가져옵니다.|  
|[GetArrayObjectInfo 메서드](icorprofilerinfo2-getarrayobjectinfo-method.md)|배열 개체에 대 한 자세한 정보를 가져옵니다.|  
|[GetBoxClassLayout 메서드](icorprofilerinfo2-getboxclasslayout-method.md)|Boxing 된 지정 된 값 형식에 대 한 클래스 레이아웃 정보를 가져옵니다.|  
|[GetClassFromTokenAndTypeArgs 메서드](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|지정 된 `ClassID` 메타 데이터 토큰 및 `ClassID` 모든 형식 인수 값을 사용 하 여 형식의를 가져옵니다.|  
|[GetClassIDInfo2 메서드](icorprofilerinfo2-getclassidinfo2-method.md)|지정 된 제네릭 클래스의 부모 모듈, 클래스에 대 한 메타 데이터 토큰, `ClassID` 부모 클래스의 및 `ClassID` 클래스의 각 형식 인수 (있는 경우)를 가져옵니다.|  
|[GetClassLayout 메서드](icorprofilerinfo2-getclasslayout-method.md)|지정된 클래스에서 정의된 필드의 레이아웃(메모리)에 대한 정보를 가져옵니다. 즉, 이 메서드는 클래스의 필드 오프셋을 가져옵니다.|  
|[GetCodeInfo2 메서드](icorprofilerinfo2-getcodeinfo2-method.md)|지정된 `FunctionID`와 연결된 네이티브 코드의 범위를 가져옵니다.|  
|[GetContextStaticAddress 메서드](icorprofilerinfo2-getcontextstaticaddress-method.md)|지정 된 컨텍스트 범위에 있는 지정 된 컨텍스트 정적 필드의 주소를 가져옵니다.|  
|[GetFunctionFromTokenAndTypeArgs 메서드](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|지정 된 `FunctionID` 메타 데이터 토큰, 클래스 포함, `ClassID` 모든 형식 인수 값을 사용 하 여 함수의를 가져옵니다.|  
|[GetFunctionInfo2 메서드](icorprofilerinfo2-getfunctioninfo2-method.md)|함수의 부모 클래스, 메타데이터 토큰 및 각 형식 인수 `ClassID`(있는 경우)를 가져옵니다.|  
|[GetGenerationBounds 메서드](icorprofilerinfo2-getgenerationbounds-method.md)|가비지 수집 힙의 세대를 구성 하는 메모리 영역 (힙의 세그먼트)을 가져옵니다.|  
|[GetNotifiedExceptionClauseInfo 메서드](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|`catch` / `finally` / `filter` 실행 되거나 방금 실행 된 예외 절 ()에 대 한 기본 주소 및 프레임 정보를 가져옵니다.|  
|[GetObjectGeneration 메서드](icorprofilerinfo2-getobjectgeneration-method.md)|지정 된 개체를 포함 하는 힙의 세그먼트를 가져옵니다.|  
|[GetRVAStaticAddress 메서드](icorprofilerinfo2-getrvastaticaddress-method.md)|지정 된 RVA (상대 가상 주소) 정적 필드의 주소를 가져옵니다.|  
|[GetStaticFieldInfo 메서드](icorprofilerinfo2-getstaticfieldinfo-method.md)|지정 된 필드가 정적으로 지정 된 범위를 가져옵니다.|  
|[GetStringLayout 메서드](icorprofilerinfo2-getstringlayout-method.md)|문자열 개체의 레이아웃 정보를 가져옵니다.|  
|[GetThreadAppDomain 메서드](icorprofilerinfo2-getthreadappdomain-method.md)|지정 된 스레드가 현재 실행 중인 코드의 응용 프로그램 도메인 ID를 가져옵니다.|  
|[GetThreadStaticAddress 메서드](icorprofilerinfo2-getthreadstaticaddress-method.md)|지정 된 스레드의 범위에 있는 지정 된 스레드 정적 필드의 주소를 가져옵니다.|  
|[SetEnterLeaveFunctionHooks2 메서드](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.|  
  
## <a name="remarks"></a>설명  

 프로파일러에서는 인터페이스의 메서드를 호출 `ICorProfilerInfo2` 하 여 CLR과 통신 하 여 이벤트 모니터링과 요청 정보를 제어 합니다.  
  
 인터페이스의 메서드는 `ICorProfilerInfo2` 자유 스레드된 모델을 사용 하 여 CLR에 의해 구현 됩니다. 각 메서드가 HRESULT를 반환하여 성공 또는 실패를 나타냅니다. 가능한 반환 코드 목록은 CorError.h 파일을 참조하세요.  
  
 CLR은 `ICorProfilerInfo2` [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)의 프로파일러 구현을 사용 하 여 초기화 하는 동안 각 코드 프로파일러에 인터페이스를 전달 합니다. 그런 다음 코드 프로파일러는 인터페이스의 메서드를 호출 `ICorProfilerInfo2` 하 여 CLR의 컨트롤에서 실행 되는 관리 코드에 대 한 정보를 가져올 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
