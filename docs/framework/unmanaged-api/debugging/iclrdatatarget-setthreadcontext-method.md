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
ms.openlocfilehash: b8c4b4e585bba4df39a743273221f38ce14a9b9d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860524"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext 메서드
대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다. 이 메서드는 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.  
  
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
 진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.  
  
 `contextSize`  
 진행 컨텍스트의 크기입니다.  
  
 `context`  
 진행 컨텍스트를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `context` 버퍼의 데이터는 Win32 `CONTEXT` 구조의 형식이 됩니다. 컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 `CONTEXT` 구조의 정의는 프로세서의 아키텍처에 따라 달라 집니다. Win32 `CONTEXT` 구조체의 정의는 winnt.exe 헤더 파일을 참조 하세요.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
