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
ms.openlocfilehash: 3afb89a42d7e26c5e89e6f9458ef3406cc0102ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684189"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID 함수

지정 된을 사용 하 여 클래스에 대 한 적절 한 CLR (공용 언어 런타임) 버전 정보를 가져옵니다 `CLSID` .  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
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
 진행  `CLSID` 구성 요소의입니다.  
  
 `pVersion`  
 제한이  성공적으로 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 진행  버퍼의 크기 (와이드 문자) `pVersion` 입니다.  
  
 `dwLength`  
 제한이 반환 된 버퍼의 길이 (바이트)입니다.  
  
 `dwResolutionFlags`  
 진행  CLSID_RESOLUTION_FLAGS 값 중 하나입니다. 지원되는 값은 다음과 같습니다.  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) 기본 interop 동작을 사용 하도록 지정 합니다.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 shim 정책을 적용 하도록 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|함수에서을 (를) 반환 했습니다.|  
|E_INVALIDARG|매개 변수 중 하나에 잘못 된 형식 또는 형식이 있습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion`버퍼가 작아서 전체 버전 문자열을 저장할 수 없습니다.|  
|REGDB_E_CLASSNOTREG|지정 된에 등록 된 클래스가 없는 경우 `CLSID`|  
|E_POINTER|`dwLength` 가 null 이거나 `cchBuffer` 버전 문자열을 저장할 수 있을 만큼 크지만 `pVersion` 가 null 인 경우|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참조

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
