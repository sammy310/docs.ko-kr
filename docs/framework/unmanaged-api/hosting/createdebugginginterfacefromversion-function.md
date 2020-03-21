---
title: CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176450"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion 함수
지정된 버전 정보를 기반으로 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 개체를 만듭니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다. 대신 공통 언어 런타임(CLR) 2.0에 대한 인터페이스를 얻으려면 [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드를 사용하고 클래스 식별자 CLSID_CLRDebuggingLegacy 및 인터페이스 식별자를 IID_ICorDebug 지정합니다. CLR 4 이상에 대한 인터페이스를 얻으려면 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수를 호출하고 클래스 식별자 CLSID_CLRDebugging 및 인터페이스 식별자를 IID_ICLRDebugging 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `iDebuggerVersion`  
 【인】 `ICorDebug` 디버거에서 이 버전이 예상됩니다. 유효한 값은 [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) 열거를 참조하십시오.  
  
 `szDebuggeeVersion`  
 【인】 디버깅할 응용 프로그램 또는 프로세스와 연결된 공통 언어 런타임 버전입니다. 이 값을 검색하는 방법에 대한 자세한 내용은 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) 메서드를 참조하십시오.  
  
 `ppCordb`  
 【아웃】 개체에 대한 포인터를 `ICorDebug` 받는 위치입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음 값 외에 WinError.h 파일에 정의된 표준 COM 오류 코드를 반환합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szDebuggeeVersion`또는 `ppCordb` null이거나 버전 문자열이 올바르지 않습니다.|  
  
## <a name="remarks"></a>설명  
 매개 `szDebuggeeVersion` 변수는 MSCorDbi.dll의 해당 버전에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
