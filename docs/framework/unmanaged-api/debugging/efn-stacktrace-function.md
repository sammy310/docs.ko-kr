---
title: _EFN_StackTrace 함수
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 687fdd0735e6cb0f3a727c8a2da3cf33bffb6a39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738975"
---
# <a name="efnstacktrace-function"></a>\_EFN\_StackTrace 함수
비관리 코드와 관리 코드 간 각 전환에 대해 하나씩, `CONTEXT` 레코드 배열 및 관리되는 스택 추적의 텍스트 표시를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Client`  
 [in] 디버깅 중인 클라이언트입니다.  
  
 `wszTextOut`  
 [out] 스택 추적의 텍스트 표현입니다.  
  
 `puiTextLength`  
 [out] 에 있는 문자의 수에 대 한 포인터 `wszTextOut`합니다.  
  
 `pTransitionContexts`  
 [out] 컨텍스트 전환의 배열입니다.  
  
 `puiTransitionContextCount`  
 [out] 배열에서 컨텍스트 전환 수에 대 한 포인터입니다.  
  
 `uiSizeOfContext`  
 [in] 상황에 맞는 구조체의 크기입니다.  
  
 `Flags`  
 [in] 0 또는 SOS_STACKTRACE_SHOWADDRESSES (0x01) EBP 레지스터 및 각 앞에 입력 스택 포인터 ESP ()를 표시 하도록로 `module!functionname` 줄.  
  
## <a name="remarks"></a>설명  
 `_EFN_StackTrace` WinDbg 프로그래밍 인터페이스에서 구조를 호출할 수 있습니다. 매개 변수는 다음과 같이 사용 됩니다.  
  
- 하는 경우 `wszTextOut` isnull 및 `puiTextLength` 는 null이 아닌 함수에서 문자열 길이 반환 `puiTextLength`합니다.  
  
- 하는 경우 `wszTextOut` 가 null이 아닌 함수에 텍스트를 저장 `wszTextOut` 가리키는 위치까지 `puiTextLength`입니다. 버퍼 길이가 짧습니다 경우 충분 한 공간이 버퍼 또는 e_outofmemory가 반환 되었으면 성공적으로 반환 합니다.  
  
- 전환에 대 한 부분 함수는 무시 됩니다 `pTransitionContexts` 고 `puiTransitionContextCount` 둘 다 null입니다. 이 경우 함수는 함수 이름만의 텍스트 출력을 사용 하 여 호출자에 게 제공합니다.  
  
- 경우 `pTransitionContexts` isnull 및 `puiTransitionContextCount` 는 null이 아닌 반환에서 상황에 맞는 항목 수가 필요한 `puiTransitionContextCount`합니다.  
  
- 하는 경우 `pTransitionContexts` 가 null이 아닌 함수 처리 길이의 구조의 배열로 `puiTransitionContextCount`합니다. 구조체의 크기가 지정 하 여 `uiSizeOfContext`, 크기 여야 [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) 또는 `CONTEXT` 아키텍처에 대 한 합니다.  
  
- `wszTextOut` 다음 형식으로 기록 됩니다.  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- 16 진수 오프셋 0x0 인 경우 오프셋 없이 기록 됩니다.  
  
- 경우에 관리 코드가 없는 스레드에서 현재 컨텍스트에서 SOS_E_NOMANAGEDCODE 반환 합니다.  
  
- 합니다 `Flags` 매개 변수는 0 또는 각 앞에 EBP 및 ESP를 보려는 SOS_STACKTRACE_SHOWADDRESSES `module!functionname` 줄. 기본적으로 0입니다.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** SOS_Stacktrace.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
