---
title: ICLRDataTarget::Request 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 4d0cf22b4b0644d6b25d6b3ef884718cb9ca1e42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723794"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request 메서드

구현에 정의 된 대로 작업을 요청 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `reqCode`  
 진행 사용자 정의.  
  
 `inBufferSize`  
 진행 들어오는 요청에 사용 되는 입력 버퍼의 크기입니다.  
  
 `inBuffer`  
 진행 요청을 포함 하는 버퍼입니다.  
  
 `outBufferSize`  
 진행 응답에 사용 되는 출력 버퍼의 크기입니다.  
  
 `outBuffer`  
 제한이 응답을 포함 하는 버퍼입니다.  
  
## <a name="remarks"></a>설명  

 메서드는 지정 `Request` 되지 않은 사용자 지정 작업의 추가를 용이 하 게 합니다. 즉,이 메서드는 인터페이스 정의를 수정할 필요 없이 확장성을 제공 합니다.  
  
 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
