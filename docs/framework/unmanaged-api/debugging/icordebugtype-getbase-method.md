---
title: ICorDebugType::GetBase 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379993"
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase 메서드
이가 나타내는 형식의 기본 형식 (있는 경우)을 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBase`  
 제한이 기본 형식을 나타내는 개체의 주소에 대 한 포인터입니다 `ICorDebugType` .  
  
## <a name="remarks"></a>설명  
 형식에 대 한 기본 형식을 조회 하는 것은 개체 또는 해당 부모 클래스의 모든 필드를 인쇄 하는 등의 일반적인 디버거 기능을 구현 하는 데 유용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
