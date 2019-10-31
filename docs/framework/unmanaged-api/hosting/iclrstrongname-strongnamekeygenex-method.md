---
title: ICLRStrongName::StrongNameKeyGenEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: 1a5bcfb7a272af694126025f28ca3efe5a881c15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135016"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>ICLRStrongName::StrongNameKeyGenEx 메서드
강력한 이름 사용을 위해 지정 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszKeyContainer`  
 진행 요청 된 키 컨테이너 이름입니다. 임시 이름을 생성 하려면 `wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이어야 합니다.  
  
 `dwFlags`  
 진행 키를 등록 된 상태로 유지할지 여부를 지정 하는 값입니다. 다음 값이 지원 됩니다.  
  
- 0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.  
  
- 0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.  
  
 `dwKeySize`  
 진행 요청 된 키 크기 (비트)입니다.  
  
 `ppbKeyBlob`  
 제한이 반환 된 공개/개인 키 쌍입니다.  
  
 `pcbKeyBlob`  
 제한이 `ppbKeyBlob`의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).  
  
## <a name="remarks"></a>주의  
 .NET Framework 버전 1.0 및 1.1에는 강력한 이름의 어셈블리에 서명 하는 데 1024 비트의 `dwKeySize` 필요 합니다. 버전 2.0에는 2048 비트 키에 대 한 지원 기능이 추가 되었습니다.  
  
 키를 검색 한 후에는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameKeyGen 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
