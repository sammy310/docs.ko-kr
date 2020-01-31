---
title: 프로파일링 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860868"
---
# <a name="profiling-global-static-functions"></a>프로파일링 전역 정적 함수
이 섹션에서는 프로 파일링 API에서 사용 하는 관리 되지 않는 API 함수에 대해 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET Framework 버전 1 프로 파일링 함수  
 [FunctionEnter 함수](functionenter-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
 [FunctionLeave 함수](functionleave-function.md)  
 함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
 [FunctionTailcall 함수](functiontailcall-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다. .NET Framework 2.0에서 사용 되지 않습니다.  
  
## <a name="net-framework-version-2-profiling-functions"></a>.NET Framework 버전 2 프로 파일링 함수  
 [FunctionIDMapper 함수](functionidmapper-function.md)  
 함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다. 또한 프로파일러를 사용 하 여 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.  
  
 [FunctionEnter2 함수](functionenter2-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [FunctionLeave2 함수](functionleave2-function.md)  
 함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [FunctionTailcall2 함수](functiontailcall2-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다. .NET Framework 4에서 사용 되지 않습니다.  
  
 [StackSnapshotCallback 함수](stacksnapshotcallback-function.md)  
 [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.  
  
## <a name="net-framework-version-4-profiling-functions"></a>.NET Framework 버전 4 프로 파일링 함수  
 [FunctionIDMapper2 함수](functionidmapper2-function.md)  
 함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md),[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다. 또한 프로파일러는 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.  
  
 `FunctionIDMapper2`는 `clientData` 매개 변수를 사용 하 여 [Functionidmapper](functionidmapper-function.md) 함수를 확장 합니다 .이 함수는 프로파일러를 사용 하 여 런타임을 명확 하 게 구분할 수  
  
 [FunctionEnter3 함수](functionenter3-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.  
  
 [FunctionEnter3WithInfo 함수](functionenter3withinfo-function.md)  
 컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고, [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) 에 전달 하 여 스택 프레임 및 함수 인수를 검색 하는 핸들을 제공 합니다.  
  
 [FunctionLeave3 함수](functionleave3-function.md)  
 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알립니다.  
  
 [FunctionLeave3WithInfo 함수](functionleave3withinfo-function.md)  
 는 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알리고 스택 프레임 및 반환 값을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.  
  
 [FunctionTailcall3 함수](functiontailcall3-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.  
  
 [FunctionTailcall3WithInfo 함수](functiontailcall3withinfo-function.md)  
 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.  
  
## <a name="related-sections"></a>관련 섹션  
 [프로파일링 개요](profiling-overview.md)  
  
 [프로파일링 인터페이스](profiling-interfaces.md)  
  
 [프로파일링 열거형](profiling-enumerations.md)  
  
 [프로파일링 구조체](profiling-structures.md)
