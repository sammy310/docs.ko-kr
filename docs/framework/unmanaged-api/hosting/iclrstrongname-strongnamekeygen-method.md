---
description: '자세히 알아보기: ICLRStrongName:: StrongNameKeyGen 메서드'
title: ICLRStrongName::StrongNameKeyGen 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: c445e1f0290d907f7820c0000f602f2668f59103
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799562"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>ICLRStrongName::StrongNameKeyGen 메서드

강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `wszKeyContainer`  
 진행 요청 된 키 컨테이너 이름입니다. `wszKeyContainer` 임시 이름을 생성 하려면 비어 있지 않은 문자열 이거나 null 이어야 합니다.  
  
 `dwFlags`  
 진행 키를 등록 된 상태로 유지할지 여부를 지정 하는 값입니다. 지원되는 값은 다음과 같습니다.  
  
- 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하기 위해가 null 일 때 사용 됩니다.  
  
- 0x00000001 ( `SN_LEAVE_KEY` )-키를 등록 된 상태로 유지 하도록 지정 합니다.  
  
 `ppbKeyBlob`  
 제한이 반환 된 공개/개인 키 쌍입니다.  
  
 `pcbKeyBlob`  
 제한이 의 크기 (바이트)입니다 `ppbKeyBlob` .  
  
## <a name="return-value"></a>Return Value  

 `S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="remarks"></a>설명  

 [ICLRStrongName:: StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) 메서드는 1024 비트 키를 만듭니다. 키를 검색 한 후에는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameKeyGenEx 메서드](iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
