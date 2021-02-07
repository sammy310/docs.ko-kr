---
description: '자세히 알아보기: CreateDebuggingInterfaceFromVersion 함수'
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
ms.openlocfilehash: 163ada49f028071b48c93ee3c565152a773782ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760632"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion 함수

지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.  
  
 이 함수는 .NET Framework 4에서 사용 되지 않습니다. 대신 CLR (공용 언어 런타임) 2.0에 대 한 인터페이스를 가져오려면 [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) 메서드를 사용 하 고 클래스 식별자 CLSID_CLRDebuggingLegacy 및 인터페이스 식별자 IID_ICorDebug를 지정 합니다. CLR 4 이상에 대 한 인터페이스를 가져오려면 [Clrcreateinstance](clrcreateinstance-function.md) 함수를 호출 하 고 클래스 식별자 CLSID_CLRDebugging 및 인터페이스 식별자 IID_ICLRDebugging를 지정 합니다.  
  
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
 진행 디버거에 필요한의 버전입니다 `ICorDebug` . 올바른 값은 [Cordebuginterfaceversion](../debugging/cordebuginterfaceversion-enumeration.md) 열거형을 참조 하세요.  
  
 `szDebuggeeVersion`  
 진행 디버그할 응용 프로그램 또는 프로세스와 연결 된 공용 언어 런타임 버전입니다. 이 값을 검색 하는 방법에 대 한 자세한 내용은 [Getversionfromprocess](getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) 메서드를 참조 하세요.  
  
 `ppCordb`  
 제한이 개체에 대 한 포인터를 수신 하는 위치입니다 `ICorDebug` .  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음 값 외에도 Winerror.h 파일에 정의 된 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szDebuggeeVersion` 또는 `ppCordb` 이 null 이거나 버전 문자열이 잘못 되었습니다.|  
  
## <a name="remarks"></a>설명  

 `szDebuggeeVersion`매개 변수는 해당 하는 버전의 MSCorDbi.dll에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
