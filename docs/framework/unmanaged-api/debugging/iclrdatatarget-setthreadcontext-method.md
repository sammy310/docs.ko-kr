---
title: ICLRDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179124"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext 메서드
대상 프로세스에서 지정된 스레드의 현재 컨텍스트를 설정합니다. 이 메서드는 공통 언어 런타임(CLR) 데이터 액세스 서비스에서 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadID`  
 【인】 대상 프로세스에서 스레드의 운영 체제 식별자입니다.  
  
 `contextSize`  
 【인】 컨텍스트의 크기입니다.  
  
 `context`  
 【인】 컨텍스트를 포함하는 버퍼에 대한 포인터입니다.  
  
 버퍼의 `context` 데이터는 Win32 `CONTEXT` 구조의 형식입니다. 컨텍스트는 프로세서별 레지스터 데이터를 지정하므로 Win32 `CONTEXT` 구조의 정의는 프로세서의 아키텍처에 따라 달라집니다. Win32 `CONTEXT` 구조의 정의에 대 한 WinNT.h 헤더 파일을 참조 하십시오.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 클러데이터.아이들, 클러데이터.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
