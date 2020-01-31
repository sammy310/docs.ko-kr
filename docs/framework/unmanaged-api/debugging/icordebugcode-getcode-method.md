---
title: ICorDebugCode::GetCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: 14a72e4622aac09840e43f8bcdcf8a8c8d6e6892
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777909"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode 메서드
지정 된 함수에 대 한 코드를 모두 가져오고 디스어셈블리에 맞게 형식이 지정 됩니다. 이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다. 대신 [ICorDebugCode2:: GetCodeChunks](icordebugcode2-getcodechunks-method.md) 를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `startOffset`  
 진행 함수 시작의 오프셋입니다.  
  
 `endOffset`  
 진행 함수 끝의 오프셋입니다.  
  
 `cBufferAlloc`  
 진행 코드가 반환 될 `buffer` 배열의 크기입니다.  
  
 `buffer`  
 제한이 코드가 반환 되는 배열입니다.  
  
 `pcBufferSize`  
 제한이 반환 된 바이트 수입니다.  
  
## <a name="remarks"></a>주의  
 함수의 코드가 여러 청크로 분할 된 경우에는 기본 오프셋의 오름차순으로 연결 됩니다. 명령 경계는 확인 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참조

- [GetCodeChunks 메서드](icordebugcode2-getcodechunks-method.md)
