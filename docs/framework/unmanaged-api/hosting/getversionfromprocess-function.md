---
description: '자세한 정보: GetVersionFromProcess 함수'
title: GetVersionFromProcess 함수
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: ab665d2984f79baf049009690b36782528094937
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785252"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 함수

지정 된 프로세스 핸들과 연결 된 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `hProcess`  
 진행 프로세스에 대 한 핸들입니다.  
  
 `pVersion`  
 제한이 메서드가 성공적으로 완료 되 면 버전 번호 문자열이 포함 된 버퍼입니다.  
  
 `cchBuffer`  
 진행 버전 버퍼의 길이입니다.  
  
 `pdwLength`  
 제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`pVersion` 가 null이 고 `cchBuffer` 가 null이 아니거나 그 반대의 경우도 마찬가지입니다.<br /><br /> 또는<br /><br /> `hProcess` 는 프로세스에 대 한 유효한 핸들이 아닙니다.<br /><br /> 또는<br /><br /> CLR이 로드 되지 않았습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` 가 null 이거나 버전 문자열의 길이 보다 작은 경우|  
|E_NOTIMPL|이 방법은 Microsoft windows 95, Microsoft Windows 98 또는 Microsoft Windows Millennium Edition 운영 체제에서 사용할 수 없습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetRequestedRuntimeInfo 함수](getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion 함수](getrequestedruntimeversion-function.md)
- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
