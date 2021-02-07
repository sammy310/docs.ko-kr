---
description: '다음에 대 한 자세한 정보: CorLaunchApplication 함수'
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
ms.openlocfilehash: 89f1f37ddde69fb5ecc24fd9dfd0d0c27d5fac40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716954"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication 함수

지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 [HOST_TYPE](host-type-enumeration.md) 열거형의 값입니다.  
  
 `pwzAppFullName`  
 진행 시작 되는 응용 프로그램의 전체 이름입니다.  
  
 `dwManifestPaths`  
 진행 응용 프로그램에 대 한 매니페스트 경로 수입니다.  
  
 `ppwzManifestPaths`  
 진행 시작 중인 응용 프로그램에 대 한 매니페스트의 경로를 지정 하는 문자열의 배열입니다.  
  
 `dwActivationData`  
 진행 시작 중인 응용 프로그램에 대 한 활성화 데이터 항목의 수입니다.  
  
 `ppwzActivationData`  
 진행 시작 중인 응용 프로그램에 대 한 활성화 데이터 항목인 각각의 문자열 배열입니다.  
  
 `lpProcessInformation`  
 제한이 응용 프로그램이 로드 된 프로세스에 대 한 정보에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
