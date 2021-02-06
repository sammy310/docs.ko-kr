---
description: '자세히 알아보기: StrongNameTokenFromPublicKey 함수'
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
ms.openlocfilehash: f978c9b2727db4b293b9c92a8789fbf9ba749d41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636284"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey 함수

공개 키를 나타내는 토큰을 가져옵니다. 강력한 이름 토큰은 공개 키의 축약 된 형태입니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pbPublicKeyBlob`  
 진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조체입니다.  
  
 `cbPublicKeyBlob`  
 진행 의 크기 (바이트)입니다 `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 제한이 전달 된 키에 해당 하는 강력한 이름 토큰 `pbPublicKeyBlob` 입니다. 공용 언어 런타임은 토큰을 반환할 메모리를 할당 합니다. 호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 메모리를 해제 해야 합니다.  
  
 `pcbStrongNameToken`  
 제한이 반환 된 강력한 이름 토큰의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  

 `true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 강력한 이름 토큰은 키 정보를 메타 데이터에 저장할 때 공간을 절약 하는 데 사용 되는 공개 키의 축약 된 형태입니다. 특히 강력한 이름 토큰은 어셈블리 참조에서 종속 어셈블리를 참조 하는 데 사용 됩니다.  
  
 `StrongNameTokenFromPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** mscoree.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameTokenFromPublicKey 메서드](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey 메서드](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob 구조체](publickeyblob-structure.md)
