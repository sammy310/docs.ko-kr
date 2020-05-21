---
title: ICLRStrongName::StrongNameGetBlobFromImage 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: 82e18db2f5b911f0e7895959119edd7d2c722f3b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763135"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>ICLRStrongName::StrongNameGetBlobFromImage 메서드
지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbBase`  
 진행 매핑된 어셈블리 매니페스트의 메모리 주소입니다.  
  
 `dwLength`  
 진행 에 있는 이미지의 크기 (바이트)입니다 `pbBase` .  
  
 `pbBlob`  
 진행 이미지의 이진 표현을 포함 하는 버퍼입니다.  
  
 `pcbBlob`  
 [in, out] 요청 된 최대 크기 (바이트)입니다 `pbBlob` . 반환 시의 실제 크기 (바이트)입니다 `pbBlob` .  
  
## <a name="return-value"></a>Return Value  
 `S_OK`메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameGetBlob 메서드](iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
