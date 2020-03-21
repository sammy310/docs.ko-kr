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
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178993"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode 메서드
디스어셈블리에 대한 서식이 지정된 함수에 대한 모든 코드를 가져옵니다. 이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용되지 않습니다. 대신 [ICorDebugCode2::GetCodeChunks를](icordebugcode2-getcodechunks-method.md) 사용합니다.  
  
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
 【인】 함수 시작 부분의 오프셋입니다.  
  
 `endOffset`  
 【인】 함수 끝의 오프셋입니다.  
  
 `cBufferAlloc`  
 【인】 코드가 반환될 `buffer` 배열의 크기입니다.  
  
 `buffer`  
 【아웃】 코드가 반환되는 배열입니다.  
  
 `pcBufferSize`  
 【아웃】 반환된 바이트 수입니다.  
  
## <a name="remarks"></a>설명  
 함수의 코드가 여러 청크로 분할된 경우 네이티브 오프셋을 늘리는 순서로 연결됩니다. 명령 경계는 선택되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET 프레임워크 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고 항목

- [GetCodeChunks 메서드](icordebugcode2-getcodechunks-method.md)
