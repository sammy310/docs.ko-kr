---
description: '자세히 알아보기: ICorDebugDataTarget:: ReadVirtual 메서드'
title: ICorDebugDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 4525ba1e5dc685813d963dab96879b886987f38f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710610"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual 메서드

지정 된 주소에서 시작 하는 연속 메모리 블록을 가져와 제공 된 버퍼에 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>매개 변수  

 `address`  
 진행 요청 된 메모리의 시작 주소입니다.  
  
 `pbuffer`  
 제한이 메모리가 저장 될 버퍼입니다.  
  
 `bytesRequested`  
 진행 대상 주소에서 가져올 바이트 수입니다.  
  
 `pBytesRead`  
 제한이 실제로 대상 주소에서 읽은 바이트 수입니다. 이는 보다 적을 수 있습니다 `bytesRequested` .  
  
## <a name="remarks"></a>설명  

 지정 된 시작 주소에서 첫 번째 바이트를 읽을 수 있는 경우 호출은 null 종료 문자열과 같이 자체 설명 길이를 사용 하 여 데이터 구조를 효율적으로 읽을 수 있도록 성공을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugDataTarget 인터페이스](icordebugdatatarget-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
