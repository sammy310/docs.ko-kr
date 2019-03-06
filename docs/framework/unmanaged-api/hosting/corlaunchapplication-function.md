---
title: CorLaunchApplication 함수
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e10a92b1748fcdf518fa68cb7054731f4511396b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487189"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication 함수
지정한 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.  
  
 이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwClickOnceHost`  
 [in] 값을 [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) 응용 프로그램을 시작 하는 호스트의 형식을 지정 하는 열거형입니다.  
  
 `pwzAppFullName`  
 [in] 실행 하는 응용 프로그램의 전체 이름입니다.  
  
 `dwManifestPaths`  
 [in] 응용 프로그램에 대 한 매니페스트 경로의 수입니다.  
  
 `ppwzManifestPaths`  
 [in] 실행 하는 응용 프로그램에 대 한 매니페스트 경로 지정 하는 각 문자열의 배열입니다.  
  
 `dwActivationData`  
 [in] 실행 하는 응용 프로그램에 대 한 활성화 데이터 항목의 수입니다.  
  
 `ppwzActivationData`  
 [in] 실행 하는 응용 프로그램에 대 한 활성화 데이터 항목은 각 문자열의 배열입니다.  
  
 `lpProcessInformation`  
 [out] 응용 프로그램을 로드 하는 프로세스에 대 한 정보에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
