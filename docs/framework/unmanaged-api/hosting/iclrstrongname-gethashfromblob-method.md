---
title: ICLRStrongName::GetHashFromBlob 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 0c9adcc252fe16c95da8b2afca45bb2ee5dc545a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135198"
---
# <a name="iclrstrongnamegethashfromblob-method"></a>ICLRStrongName::GetHashFromBlob 메서드
지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbBlob`  
 진행 해시할 메모리 블록의 주소에 대 한 포인터입니다.  
  
 `cchBlob`  
 진행 메모리 블록의 길이 (바이트)입니다.  
  
 `piHashAlg`  
 [in, out] 해시 알고리즘을 지정 하는 상수입니다. 기본 알고리즘에는 0을 사용 합니다.  
  
 `pbHash`  
 제한이 반환 된 해시 버퍼입니다.  
  
 `cchHash`  
 진행 `pbHash`요청 된 최대 크기입니다.  
  
 `pchHash`  
 제한이 반환 된 `pbHash`의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
