---
title: GetRequestedRuntimeInfo 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178148"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo 함수
응용 프로그램에서 요청한 공통 언어 런타임(CLR)에 대한 버전 및 디렉터리 정보를 가져옵니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,
    [in]  LPCWSTR  pwszVersion,
    [in]  LPCWSTR  pConfigurationFile,
    [in]  DWORD    startupFlags,
    [in]  DWORD    runtimeInfoFlags,
    [out] LPWSTR   pDirectory,
    [in]  DWORD    dwDirectory,
    [out] DWORD   *dwDirectoryLength,
    [out] LPWSTR   pVersion,
    [in]  DWORD    cchBuffer,
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pExe`  
 【인】 응용 프로그램의 이름입니다.  
  
 `pwszVersion`  
 【인】 런타임의 버전 번호를 지정하는 문자열입니다.  
  
 `pConfigurationFile`  
 【인】 와 연결된 구성 파일의 이름입니다. `pExe`  
  
 `startupFlags`  
 【인】 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거 값 중 하나 이상입니다.  
  
 `runtimeInfoFlags`  
 【인】 [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) 열거 값 중 하나 이상입니다.  
  
 `pDirectory`  
 【아웃】 성공적으로 완료되면 런타임에 대한 디렉터리 경로를 포함하는 버퍼입니다.  
  
 `dwDirectory`  
 【인】 디렉터리 버퍼의 길이입니다.  
  
 `dwDirectoryLength`  
 【아웃】 디렉터리 경로 문자열의 길이에 대한 포인터입니다.  
  
 `pVersion`  
 【아웃】 성공적으로 완료될 때 런타임의 버전 번호를 포함하는 버퍼입니다.  
  
 `cchBuffer`  
 【인】 버전 문자열 버퍼의 길이입니다.  
  
 `dwlength`  
 【아웃】 버전 문자열의 길이에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|디렉터리 버퍼가 디렉터리 경로를 저장할 만큼 크지 않습니다.<br /><br /> -또는-<br /><br /> 버전 버퍼가 버전 문자열을 저장할 만큼 크지 않습니다.|  
  
## <a name="remarks"></a>설명  
 메서드는 `GetRequestedRuntimeInfo` 프로세스에 로드된 버전에 대한 런타임 정보를 반환하며, 컴퓨터에 설치된 최신 버전은 아닙니다.  
  
 .NET Framework 버전 2.0에서는 다음과 같이 메서드를 사용하여 최신 `GetRequestedRuntimeInfo` 설치된 버전에 대한 정보를 얻을 수 있습니다.  
  
- `pExe`에서 및 `pwszVersion` `pConfigurationFile` 매개 변수를 null로 지정합니다.  
  
- 매개 변수에 대한 `RUNTIME_INFO_FLAGS` 열거형에 `runtimeInfoFlags` RUNTIME_INFO_UPGRADE_VERSION 플래그를 지정합니다.  
  
 메서드는 `GetRequestedRuntimeInfo` 다음과 같은 상황에서 최신 CLR 버전을 반환 하지 않습니다.  
  
- 특정 CLR 버전 로드를 지정하는 응용 프로그램 구성 파일이 있습니다. .NET Framework는 `pConfigurationFile` 매개 변수에 대해 null을 지정하는 경우에도 구성 파일을 사용합니다.  
  
- [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 메서드는 이전 CLR 버전을 지정하는 방법을 호출했습니다.  
  
- 이전 CLR 버전에 대해 컴파일된 응용 프로그램이 현재 실행 중입니다.  
  
 매개 `runtimeInfoFlags` 변수의 경우 한 번에 `RUNTIME_INFO_FLAGS` 열거형의 아키텍처 상수 중 하나만 지정할 수 있습니다.  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetRequestedRuntimeVersion 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess 함수](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
