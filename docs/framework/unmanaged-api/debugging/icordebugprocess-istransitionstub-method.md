---
title: ICorDebugProcess::IsTransitionStub 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775522"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub 메서드
관리 코드로 전환 하는 스텁을 내부 주소 인지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 [in] `CORDB_ADDRESS` 해당 주소를 지정 하는 값입니다.  
  
 `pbTransitionStub`  
 [out] 부울 값에 대 한 포인터 `true` 관리 되는 코드를 전환 하는 스텁을 내에서 지정된 된 주소 이면 그렇지 않은 경우 *`pbTransitionStub` 는 `false`합니다.  
  
## <a name="remarks"></a>설명  
 `IsTransitionStub` 메서드 수 단계별 비관리 코드에서 관리 스텝 퍼에 단계별 실행 제어를 반환 하는 시기를 결정 합니다.  
  
 이식 가능한 실행 파일 (PE) 파일에서 정보를 확인 하 여 전환 스텁을 식별할 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
