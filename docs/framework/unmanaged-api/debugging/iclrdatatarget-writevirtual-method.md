---
title: ICLRDataTarget::WriteVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: 6a7a7736837f7e6bbf1ad4982e78a75550abbeab
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860507"
---
# <a name="iclrdatatargetwritevirtual-method"></a>ICLRDataTarget::WriteVirtual 메서드
지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 진행 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS입니다.  
  
 `buffer`  
 진행 쓸 데이터를 저장 하는 버퍼에 대 한 포인터입니다.  
  
 `bytesRequested`  
 진행 쓸 바이트 수입니다.  
  
 `bytesWritten`  
 제한이 쓰여진 실제 바이트 수에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
