---
title: ICLRMetaHost::GetVersionFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6c7fd48269a3e8291a548b3e13efe5c8e70652
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150815"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>ICLRMetaHost::GetVersionFromFile 메서드
파일 경로가 지정 된 어셈블리의 원래.net 컴파일 버전을 (메타 데이터에 저장 됨)을 가져옵니다. 이 메서드를 대체 합니다 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzFilePath`  
 [in] 전체 어셈블리 파일 경로입니다.  
  
 `pwzbuffer`  
 [out] .NET Framework 컴파일 버전 메타 데이터 형식으로 저장 "v*A*. *B*[. *X*] "입니다. *A*, *B*, 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다. 이 문자열의 길이 MAX_PATH 제한 됩니다.  
  
> [!NOTE]
>  이 출력 C:\Windows\Microsoft.NET\Framework 아래 표시 된 대로.NET Framework 버전의 디렉터리 이름을 찾습니다.  
  
 예제 값은 "v1.0.3705", "v1.1.4322", "v2.0.50727" 및 "v4.0"입니다. *X*", 여기서 *X* 설치 빌드 번호에 따라 달라 집니다. "V"를 접두사는 필요 합니다.  
  
 `pcchBuffer`  
 [out에서] 크기 `pwzbuffer` 버퍼 오버런을 방지 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pwzbuffer` 또는 `pcchBuffer`이 null입니다.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|버퍼가 너무 작습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRMetaHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
