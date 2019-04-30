---
title: StrongNameTokenFromPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000287"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey 함수
공개 키를 나타내는 토큰을 가져옵니다. 강력한 이름 토큰은 공개 키의 축약 형태입니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbPublicKeyBlob`  
 [in] 형식의 구조체 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 합니다.  
  
 `cbPublicKeyBlob`  
 [in] 크기 (바이트)의 `pbPublicKeyBlob`합니다.  
  
 `ppbStrongNameToken`  
 [out] 전달 된 키에 해당 하는 강력한 이름의 토큰 `pbPublicKeyBlob`합니다. 공용 언어 런타임 토큰을 반환 하는 메모리를 할당 합니다. 호출자에 게 사용 하 여이 메모리를 해제 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.  
  
 `pcbStrongNameToken`  
 [out] 반환 된 강력한 이름 토큰의 바이트 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 강력한 이름 토큰은 축약 형태 공개 키 메타 데이터에 키 정보를 저장 하는 경우 공간을 절약 하는 데 사용 합니다. 특히, 강력한 이름 토큰 종속 어셈블리를 가리키는 어셈블리 참조에 사용 됩니다.  
  
 경우는 `StrongNameTokenFromPublicKey` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [StrongNameTokenFromPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob 구조체](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
