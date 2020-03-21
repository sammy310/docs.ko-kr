---
title: GetRequestedRuntimeVersionForCLSID 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178109"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID 함수
지정된 `CLSID`을 사용 하 이 클래스에 대 한 적절 한 공통 언어 런타임 (CLR) 버전 정보를 가져옵니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `rclsid`  
 【인】  구성 `CLSID` 요소의 입니다.  
  
 `pVersion`  
 【아웃】  성공적으로 완료되면 버전 번호 문자열이 포함된 버퍼입니다.  
  
 `cchBuffer`  
 【인】  `pVersion` 버퍼의 크기(와이드 문자)입니다.  
  
 `dwLength`  
 【아웃】 반환된 버퍼의 길이(바이트)입니다.  
  
 `dwResolutionFlags`  
 【인】  CLSID_RESOLUTION_FLAGS 값 중 하나입니다. 다음 값이 지원 됩니다.  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) 기본 interop 동작을 사용해야 하는지 지정합니다.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 shim 정책을 적용 해야 합니다 지정 합니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|함수가 성공적으로 반환되었습니다.|  
|E_INVALIDARG|매개 변수 중 하나에 잘못된 형식 또는 형식이 있습니다.|  
|ERROR_INSUFFICIENT_BUFFER|버퍼가 `pVersion` 전체 버전 문자열을 보유할 만큼 크지 않습니다.|  
|REGDB_E_CLASSNOTREG|지정된 `CLSID`에 등록된 클래스가 없습니다.|  
|E_POINTER|`dwLength`null이거나 `cchBuffer` 버전 문자열을 보유할 수 있을 `pVersion` 만큼 크지만 null입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
