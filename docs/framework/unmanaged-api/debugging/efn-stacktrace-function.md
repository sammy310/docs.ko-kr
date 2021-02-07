---
description: _EFN_StackTrace 함수에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 6092d0793967cc422e30342783ab4dfd70b33de9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738288"
---
# <a name="_efn_stacktrace-function"></a>\_EFN \_ StackTrace 함수

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
 진행 디버깅 중인 클라이언트입니다.  
  
 `wszTextOut`  
 제한이 스택 추적의 텍스트 표현입니다.  
  
 `puiTextLength`  
 제한이 의 문자 수에 대 한 포인터입니다 `wszTextOut` .  
  
 `pTransitionContexts`  
 제한이 전환 컨텍스트의 배열입니다.  
  
 `puiTransitionContextCount`  
 제한이 배열의 전환 컨텍스트 수에 대 한 포인터입니다.  
  
 `uiSizeOfContext`  
 진행 컨텍스트 구조의 크기입니다.  
  
 `Flags`  
 진행 0 또는 SOS_STACKTRACE_SHOWADDRESSES (0x01)로 설정 하 여 EBP 레지스터와 각 줄 앞에 있는 ESP (enter stack 포인터)를 표시 합니다 `module!functionname` .  
  
## <a name="remarks"></a>설명  

 이 `_EFN_StackTrace` 구조는 WinDbg 프로그래밍 인터페이스에서 호출 될 수 있습니다. 매개 변수는 다음과 같이 사용 됩니다.  
  
- `wszTextOut`가 null이 고 `puiTextLength` 가 null이 아닌 경우 함수는의 문자열 길이를 반환 `puiTextLength` 합니다.  
  
- `wszTextOut`가 null이 아닌 경우 함수는에 `wszTextOut` 지정 된 위치까지 텍스트를 저장 `puiTextLength` 합니다. 버퍼에 충분 한 공간이 있으면 성공적으로 반환 되 고 버퍼가 충분 하지 않은 경우 E_OUTOFMEMORY을 반환 합니다.  
  
- `pTransitionContexts`및가 모두 null 인 경우 함수의 전환 부분은 무시 됩니다 `puiTransitionContextCount` . 이 경우 함수는 함수 이름에 대 한 텍스트 출력을 호출자에 게 제공 합니다.  
  
- `pTransitionContexts`가 null이 고 `puiTransitionContextCount` 가 null이 아닌 경우 함수는에서 필요한 컨텍스트 항목 수를 반환 합니다 `puiTransitionContextCount` .  
  
- `pTransitionContexts`가 null이 아닌 경우 함수는이를 길이가 인 구조체의 배열로 처리 합니다 `puiTransitionContextCount` . 구조 크기는에 의해 제공 `uiSizeOfContext` 되며 [simplecontext](stacktrace-simplecontext-structure.md) 또는 아키텍처용 크기 여야 합니다 `CONTEXT` .  
  
- `wszTextOut` 는 다음과 같은 형식으로 작성 됩니다.  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Hex의 오프셋이 0x0 이면 오프셋이 기록 되지 않습니다.  
  
- 현재 컨텍스트에 있는 스레드에 관리 코드가 없으면 함수는 SOS_E_NOMANAGEDCODE 반환 합니다.  
  
- `Flags`매개 변수는 0 또는 SOS_STACKTRACE_SHOWADDRESSES 각 줄 앞에 EBP와 ESP를 표시 `module!functionname` 합니다. 기본적으로 0입니다.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 전역 정적 함수](debugging-global-static-functions.md)
