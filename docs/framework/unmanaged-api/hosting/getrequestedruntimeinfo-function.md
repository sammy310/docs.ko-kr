---
description: '자세히 알아보기: GetRequestedRuntimeInfo 함수'
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
ms.openlocfilehash: 63d0bdcd07be5727cddc0acc352e8358b5ff0090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785291"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo 함수

응용 프로그램에서 요청 하는 CLR (공용 언어 런타임)에 대 한 버전 및 디렉터리 정보를 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
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
 진행 응용 프로그램의 이름입니다.  
  
 `pwszVersion`  
 진행 런타임의 버전 번호를 지정 하는 문자열입니다.  
  
 `pConfigurationFile`  
 진행 와 연결 된 구성 파일의 이름입니다 `pExe` .  
  
 `startupFlags`  
 진행 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형 값 중 하나 이상입니다.  
  
 `runtimeInfoFlags`  
 진행 [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) 열거형 값 중 하나 이상입니다.  
  
 `pDirectory`  
 제한이 성공적으로 완료 되 면 런타임에 대 한 디렉터리 경로를 포함 하는 버퍼입니다.  
  
 `dwDirectory`  
 진행 디렉터리 버퍼의 길이입니다.  
  
 `dwDirectoryLength`  
 제한이 디렉터리 경로 문자열의 길이에 대 한 포인터입니다.  
  
 `pVersion`  
 제한이 성공적으로 완료 되 면 런타임의 버전 번호를 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 진행 버전 문자열 버퍼의 길이입니다.  
  
 `dwlength`  
 제한이 버전 문자열의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|디렉터리 버퍼가 디렉터리 경로를 저장할 만큼 크지 않습니다.<br /><br /> 또는<br /><br /> 버전 버퍼의 크기가 작아서 버전 문자열을 저장할 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 `GetRequestedRuntimeInfo`메서드는 프로세스에 로드 된 버전에 대 한 런타임 정보를 반환 합니다 .이 정보는 컴퓨터에 최신 버전이 설치 되어 있지 않아도 됩니다.  
  
 .NET Framework 버전 2.0에서는 다음과 같이 메서드를 사용 하 여 설치 된 최신 버전에 대 한 정보를 가져올 수 있습니다 `GetRequestedRuntimeInfo` .  
  
- `pExe`, `pwszVersion` 및 `pConfigurationFile` 매개 변수를 null로 지정 합니다.  
  
- `RUNTIME_INFO_FLAGS`매개 변수에 대 한 열거형에 RUNTIME_INFO_UPGRADE_VERSION 플래그를 지정 합니다 `runtimeInfoFlags` .  
  
 `GetRequestedRuntimeInfo`메서드는 다음과 같은 상황에서 최신 CLR 버전을 반환 하지 않습니다.  
  
- 특정 CLR 버전 로드를 지정 하는 응용 프로그램 구성 파일이 있습니다. 매개 변수에 null을 지정 하는 경우에도 .NET Framework는 구성 파일을 사용 합니다 `pConfigurationFile` .  
  
- 이전 CLR 버전을 지정 하 여 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 메서드를 호출 했습니다.  
  
- 이전 CLR 버전용으로 컴파일된 응용 프로그램이 현재 실행 중입니다.  
  
 `runtimeInfoFlags`매개 변수의 경우 한 번에 열거의 아키텍처 상수 중 하나만 지정할 수 있습니다 `RUNTIME_INFO_FLAGS` .  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetRequestedRuntimeVersion 함수](getrequestedruntimeversion-function.md)
- [GetVersionFromProcess 함수](getversionfromprocess-function.md)
- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
