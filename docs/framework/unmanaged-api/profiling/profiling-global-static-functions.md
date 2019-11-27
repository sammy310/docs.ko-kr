---
title: 프로파일링 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: d1d9b0a4c61ce7c3f8f9792046fb4bddf0fdfa05
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447439"
---
# <a name="profiling-global-static-functions"></a>프로파일링 전역 정적 함수
이 섹션에서는 프로 파일링 API에서 사용 하는 관리 되지 않는 API 함수에 대해 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET Framework 버전 1 프로 파일링 함수  
 [FunctionEnter 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
 [FunctionLeave 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
 [FunctionTailcall 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
## <a name="net-framework-version-2-profiling-functions"></a>.NET Framework 버전 2 프로 파일링 함수  
 [FunctionIDMapper 함수](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다. 또한 프로파일러를 사용 하 여 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.  
  
 [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [StackSnapshotCallback 함수](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.  
  
## <a name="net-framework-version-4-profiling-functions"></a>.NET Framework 버전 4 프로 파일링 함수  
 [FunctionIDMapper2 함수](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md),[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다. 또한 프로파일러는 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.  
  
 `FunctionIDMapper2`는 `clientData` 매개 변수를 사용 하 여 [Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 함수를 확장 합니다 .이 함수는 프로파일러를 사용 하 여 런타임을 명확 하 게 구분할 수  
  
 [FunctionEnter3 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.  
  
 [FunctionEnter3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고, [ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 에 전달 하 여 스택 프레임 및 함수 인수를 검색 하는 핸들을 제공 합니다.  
  
 [FunctionLeave3 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알립니다.  
  
 [FunctionLeave3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 는 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알리고 스택 프레임 및 반환 값을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.  
  
 [FunctionTailcall3 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.  
  
 [FunctionTailcall3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로파일링 개요](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
