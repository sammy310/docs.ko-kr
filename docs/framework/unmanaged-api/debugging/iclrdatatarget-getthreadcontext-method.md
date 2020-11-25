---
title: ICLRDataTarget::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 35b7bff5d4d778a429ddc1dcd0206e6e8970ee4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703501"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext 메서드

대상 프로세스의 지정 된 스레드에 대 한 현재 실행 컨텍스트를 가져옵니다. 이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `threadID`  
 진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.  
  
 `contextFlags`  
 진행 반환할 컨텍스트의 부분을 지정 하는 플래그입니다. 구현은 최소한 컨텍스트의 부분을 반환 합니다.  
  
 `contextSize`  
 진행 컨텍스트의 크기입니다.  
  
 `context`  
 제한이 컨텍스트를 저장할 버퍼에 대 한 포인터입니다.  
  
 버퍼의 데이터는 `context` Win32 구조의 형식 이어야 합니다 `CONTEXT` . 컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 구조의 정의는 `CONTEXT` 프로세서의 아키텍처에 따라 달라 집니다. Win32 구조체의 정의는 Winnt.exe 헤더 파일을 참조 하세요 `CONTEXT` .  
  
## <a name="remarks"></a>설명  

 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
