---
description: '자세히 알아보기: ICLRStrongName:: StrongNameTokenFromPublicKey 메서드'
title: ICLRStrongName::StrongNameTokenFromPublicKey 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: de245b151e5ca016a00793a8901c0fd990a3f804
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789746"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey 메서드

공개 키를 나타내는 토큰을 가져옵니다. 강력한 이름 토큰은 공개 키의 축약 된 형태입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pbPublicKeyBlob`  
 진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) 형식의 구조체입니다.  
  
 `cbPublicKeyBlob`  
 진행 의 크기 (바이트)입니다 `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 제한이 전달 된 키에 해당 하는 강력한 이름 토큰 `pbPublicKeyBlob` 입니다. 공용 언어 런타임은 토큰을 반환할 메모리를 할당 합니다. 호출자는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여이 메모리를 해제 해야 합니다.  
  
 `pcbStrongNameToken`  
 제한이 반환 된 강력한 이름 토큰의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  

 `S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="remarks"></a>설명  

 강력한 이름 토큰은 키 정보를 메타 데이터에 저장할 때 공간을 절약 하는 데 사용 되는 공개 키의 축약 된 형태입니다. 특히 강력한 이름 토큰은 어셈블리 참조에서 종속 어셈블리를 참조 하는 데 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** mscoree.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameGetPublicKey 메서드](iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob 구조체](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
