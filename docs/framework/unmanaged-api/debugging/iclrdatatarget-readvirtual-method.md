---
title: ICLRDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e2ec063d46ce9c890927391107888032e31378
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698098"
---
# <a name="iclrdatatargetreadvirtual-method"></a>ICLRDataTarget::ReadVirtual 메서드
지정된 된 버퍼에 지정 된 가상 메모리 주소에서 데이터를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 [in] 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS 합니다.  
  
 `buffer`  
 [out] 데이터를 받는 버퍼에 대 한 포인터입니다.  
  
 `bytesRequested`  
 [in] 버퍼의 길이입니다.  
  
 `bytesRead`  
 [out] 바이트 수에 대 한 포인터를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
