---
title: ICLRStrongName::GetHashFromAssemblyFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130947"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a>ICLRStrongName::GetHashFromAssemblyFileW 메서드
유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 진행 해시할 파일의 경로입니다. 이 매개 변수는 유니코드 문자열 이어야 합니다.  
  
 `piHashAlg`  
 [in, out] 해시 알고리즘을 지정 하는 상수입니다. 기본 해시 알고리즘에 대해 0을 사용 합니다.  
  
 `pbHash`  
 제한이 반환 된 해시 버퍼입니다.  
  
 `cchHash`  
 진행 `pbHash`요청 된 최대 크기입니다.  
  
 `pchHash`  
 제한이 반환 되는 `pbHash`크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [GetHashFromAssemblyFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
