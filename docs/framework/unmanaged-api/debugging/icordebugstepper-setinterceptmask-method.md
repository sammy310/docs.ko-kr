---
title: ICorDebugStepper::SetInterceptMask 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: aaba751a58e5b23b98b1d0629ea3cc9e1e7a83a9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379013"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask 메서드
단계별 코드의 형식을 지정 하는 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mask`  
 진행 코드 형식을 지정 하는 CorDebugIntercept 열거형 값의 조합입니다.  
  
## <a name="remarks"></a>설명  
 인터셉터의 비트가 설정 된 경우 지정 된 가로채기 코드 형식이 발견 되 면 스텝 퍼가 완료 됩니다. 비트를 지우면 가로채기 코드를 건너뜁니다.  
  
 이 `SetInterceptMask` 메서드는 사용자의 관점에서 [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 와의 예기치 않은 상호 작용을 포함할 수 있습니다. 예를 들어 클래스 초기화 코드의 유일 하 게 표시 되는 (즉, 비 내부) 부분에 매핑 정보가 없고 STOP_NO_MAPPING_INFO 설정 되지 않은 경우 ( [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 메서드 및 CorDebugUnmappedStop 열거형 참조) 스텝 퍼는 클래스 초기화를 프로시저 단위로 실행 합니다. 기본적으로 열거형의 INTERCEPT_NONE 값만 사용 됩니다 `CorDebugIntercept` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
