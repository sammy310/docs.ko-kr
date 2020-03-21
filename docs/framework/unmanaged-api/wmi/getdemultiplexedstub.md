---
title: GetDemultiplexedStub 함수(관리되지 않는 API 참조)
description: GetDemultiplexedStub 함수는 클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되도록 개체 전달자 싱크를 만듭니다.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174968"
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
【인】 [IWbemObjectSink의](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)클라이언트 의 프로세스 내 구현에 대한 포인터 .

`isLocal`  
【인】 이벤트가 로컬인지 여부를 나타내는 플래그`true`(); 그렇지 `false`않으면 .

`ppObject`  
【아웃】 클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크입니다.

## <a name="return-value"></a>반환 값

함수가 성공하면 반환 값은 `S_OK` (0)입니다.

함수가 실패하면 반환 값은 0이 아닌 오류 코드입니다. 확장 오류 정보를 얻으려면 [GetErrorInfo](geterrorinfo.md) 함수를 호출합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
