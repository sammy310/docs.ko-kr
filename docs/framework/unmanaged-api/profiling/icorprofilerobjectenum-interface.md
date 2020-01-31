---
title: ICorProfilerObjectEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: fce89cc2b3b0104ba017b7df9105dea3f6ec4e91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868228"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum 인터페이스
[Ngen.exe (네이티브 이미지 생성기)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)에 의해 생성 되는 고정 된 개체의 컬렉션을 순차적으로 반복 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](icorprofilerobjectenum-clone-method.md)|이 `ICorProfilerObjectEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.|  
|[GetCount 메서드](icorprofilerobjectenum-getcount-method.md)|컬렉션에 있는 고정 된 개체의 총 수를 가져옵니다.|  
|[Next 메서드](icorprofilerobjectenum-next-method.md)|시퀀스에서 열거자의 현재 위치부터 시작 하 여 순차적 개체 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.|  
|[Reset 메서드](icorprofilerobjectenum-reset-method.md)|이 열거자의 커서를 시퀀스의 시작 위치로 이동 합니다.|  
|[Skip 메서드](icorprofilerobjectenum-skip-method.md)|지정 된 수의 요소를 건너뛰도록 현재 위치에서이 열거자의 커서를 앞으로 이동 합니다.|  
  
## <a name="remarks"></a>주의  
 `ICorProfilerObjectEnum` 인터페이스는 열거자입니다. 배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다. 즉, 수신기는 배열 요소의 흐름을 명시적으로 제어할 수 있으므로, 많은 배열을 메서드 매개 변수로 전달 하는 것과 관련 된 문제를 방지할 수 있습니다.  
  
 [ICorProfilerInfo2:: EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md) 를 사용 하 여 `ICorProfilerObjectEnum` 인터페이스에 대 한 포인터를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [EnumModuleFrozenObjects 메서드](icorprofilerinfo2-enummodulefrozenobjects-method.md)
