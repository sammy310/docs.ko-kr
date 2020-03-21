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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179109"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request 메서드
구현에 정의된 대로 작업을 요청하기 위해 공통 언어 런타임(CLR) 데이터 액세스 서비스에서 호출합니다.  
  
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
 【인】 사용자 정의.  
  
 `inBufferSize`  
 【인】 들어오는 요청에 사용되는 입력 버퍼의 크기입니다.  
  
 `inBuffer`  
 【인】 요청을 포함하는 버퍼입니다.  
  
 `outBufferSize`  
 【인】 응답에 사용되는 출력 버퍼의 크기입니다.  
  
 `outBuffer`  
 【아웃】 응답을 포함하는 버퍼입니다.  
  
## <a name="remarks"></a>설명  
 이 `Request` 메서드는 지정되지 않은 사용자 지정 작업을 쉽게 추가합니다. 즉, 이 메서드는 인터페이스 정의의 수정없이 확장성을 제공합니다.  
  
 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 클러데이터.아이들, 클러데이터.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
