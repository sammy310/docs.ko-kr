---
title: ICorDebugCode2::GetCodeChunks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750152"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks 메서드
이 코드 개체를 구성 하는 코드의 청크를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbufSize`  
 [in] 크기는 `chunks` 배열입니다.  
  
 `pcnumChunks`  
 [out] 반환 된 청크 수는 `chunks` 배열입니다.  
  
 `chunks`  
 [out] 각각을 단일 코드 청크를 나타내는 "CodeChunkInfo" 구조체의 배열입니다. 경우 변수의 `cbufSize` 가 0 이면이 매개 변수는 null 일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 코드 청크 겹치는 되지 됩니다 및 순서는 이러한는 연결 된 여 따를 [icordebugcode:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)합니다. .NET Framework 버전 2.0의에서 Microsoft MSIL (intermediate language) 코드 개체를 구성 하는 단일 코드 청크 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
