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
ms.openlocfilehash: e285df37d83ff73fe29fe293380a4053cb5a9eea
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860558"
---
# <a name="iclrdatatargetreadvirtual-method"></a>ICLRDataTarget::ReadVirtual 메서드
지정 된 가상 메모리 주소에서 지정 된 버퍼로 데이터를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS입니다.  
  
 `buffer`  
 제한이 데이터를 받는 버퍼에 대 한 포인터입니다.  
  
 `bytesRequested`  
 진행 버퍼의 길이입니다.  
  
 `bytesRead`  
 제한이 반환 된 바이트 수에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
