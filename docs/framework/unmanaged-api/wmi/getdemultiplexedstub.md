---
title: GetDemultiplexedStub 함수 (관리 되지 않는 API 참조)
description: GetDemultiplexedStub 함수는 클라이언트에서 Windows 관리를 통해 비동기 호출을 받을 수 있도록 개체 전달자 싱크를 만듭니다.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9cc028b3300b43f8a0fb3e29f8b5ac6e1817b8c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127465"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub 함수
클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크를 만듭니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>매개 변수

`pObject`  
진행 [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)의 클라이언트 in-process 구현에 대 한 포인터입니다.

`isLocal`  
진행 이벤트가 로컬 (`true`) 인지 여부를 나타내는 플래그입니다. 그렇지 않으면 `false`합니다.

`ppObject`  
제한이 클라이언트에서 Windows 관리를 통해 비동기 호출을 받을 수 있도록 지 원하는 개체 전달자 싱크입니다.

## <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 `S_OK` (0)입니다.

함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다. 확장 오류 정보를 가져오려면 [Geterrorinfo](geterrorinfo.md) 함수를 호출 합니다.
    
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참조

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
