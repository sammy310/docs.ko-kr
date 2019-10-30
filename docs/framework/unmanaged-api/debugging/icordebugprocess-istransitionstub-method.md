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
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139392"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub 메서드
관리 코드로의 전환을 발생 시킬 스텁 내에 주소가 있는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 진행 해당 주소를 지정 하는 `CORDB_ADDRESS` 값입니다.  
  
 `pbTransitionStub`  
 제한이 지정 된 주소가 관리 코드로의 전환을 발생 시키는 스텁 안에 있는 경우 `true` 되는 부울 값에 대 한 포인터입니다. 그렇지 않으면 *`pbTransitionStub` `false`됩니다.  
  
## <a name="remarks"></a>주의  
 `IsTransitionStub` 메서드는 관리 되지 않는 단계별 코드에서 관리 되는 스텝 퍼에 대 한 단계별 제어를 반환할 시기를 결정 하는 데 사용할 수 있습니다.  
  
 PE (이식 가능한 실행 파일) 파일의 정보를 살펴보면 전환 스텁을 식별할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
